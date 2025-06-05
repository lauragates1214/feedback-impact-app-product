# Technical Architecture

## System Overview

Obwob is architected as a real-time, multi-tenant feedback collection platform with sophisticated resource hierarchy management and frictionless user experience design.

## Current Technology Stack

### Backend (Rails - Test Version)
- **Framework**: Ruby on Rails 8.0
- **Database**: PostgreSQL with comprehensive indexing
- **Real-time**: Ably for WebSocket communication
- **Testing**: RSpec with unit and integration test coverage
- **Authentication**: Custom UUID-based system with hierarchical resource validation

### Frontend
- **Framework**: React with PWA capabilities
- **Styling**: SCSS with component-based architecture  
- **Real-time Client**: Ably JavaScript SDK
- **Testing**: React Testing Library (in development)

### Migration Strategy
**Target Stack (Production - Summer 2025)**
- **Backend**: Django with Django REST Framework
- **Database**: PostgreSQL (maintaining schema structure)
- **Frontend**: React (unchanged)
- **Real-time**: Ably (unchanged)

## Database Architecture

### Core Entity Relationships

```
Organizations (1) ──→ (n) Events
Organizations (1) ──→ (n) Questions  
Organizations (1) ──→ (n) OrganizationUsers

Events (1) ──→ (n) EventQuestions
Events (1) ──→ (n) EventUsers

EventQuestions (1) ──→ (n) Answers

Users (1) ──→ (n) OrganizationUsers
Users (1) ──→ (n) Answers
```

### Key Design Patterns

**Multi-tenancy**: Organizations are isolated containers with their own questions, events, and user relationships.

**Flexible Question Management**: Questions belong to organizations but can be modified per-event through the `EventQuestions` join table, maintaining original question integrity.

**Role-based Access**: Hierarchical roles at organization level (admin/member) and event level (facilitator/participant).

**Soft Deletion**: All core entities support soft deletion with `deleted` boolean flags and appropriate indexing.

**Audit Trail**: Comprehensive timestamps and relationship tracking throughout.

## Advanced Technical Implementation

### Resource Hierarchy Validation

**The Challenge**: Ensuring that nested API requests (e.g., `/organizations/1/events/2/questions/3/answers/4`) properly validate the entire resource chain.

**The Solution**: Custom `ResourceFindable` concern using metaprogramming and recursive validation.

```ruby
# Simplified example of the resource validation pattern
module ResourceFindable
  def setup_finder_method(klass)
    klass.define_method("find_#{resource_name}") do |resource_name=outer_resource_name|
      # Validate current resource exists
      resource = validate_resource(resource_name)
      
      # Recursively validate parent chain  
      parent_name = Rails.application.config.resource_hierarchy[resource_name.to_s]&.first
      if parent_name
        parent = public_send("find_#{parent_name}", parent_name)
        validate_matching_parent(resource, parent_name, parent.id)
      end
      
      resource
    end
  end
end
```

**Key Benefits**:
- **DRY**: Single concern handles all nested resource validation
- **Dynamic**: Automatically adapts to new resource types through configuration
- **Secure**: Prevents unauthorized access to resources across organization boundaries
- **Maintainable**: Centralised logic with clear error handling

### Real-time Communication Architecture

**Ably Channel Strategy**:
- **Event Channels**: One channel per event for question broadcasting
- **Answer Channels**: Dedicated channels for response collection
- **Presence Channels**: Track active participants per event

**Message Flow**:
1. Facilitator triggers question broadcast via API
2. Backend publishes to Ably event channel
3. All participant devices receive question instantly
4. Participants submit responses via API
5. Backend broadcasts answer confirmation to facilitator channel

**Security Model**:
- Channel access controlled via server-generated Ably tokens
- Participants can only subscribe to their event's channels
- Facilitators receive additional permissions for broadcasting

### QR Code Access System

**User Creation Flow**:
1. QR code contains URL with event and role parameters
2. Frontend generates UUID for anonymous user
3. Backend creates user record and assigns to event
4. Session maintained via UUID-based tokens
5. Hierarchical resource access automatically validated
6. Optional Account Creation: Users can optionally create persistent accounts for multi-event participation and enhanced features

**Benefits**:
- **Zero Friction**: No downloads, registrations, or login processes
- **Privacy**: Anonymous participation by default, with optional account creation for enhanced features
- **Security**: UUIDs prevent user enumeration attacks
- **Scalability**: Stateless design supports high concurrent usage

## API Architecture

### RESTful Design Patterns

**Nested Resource Routes**:
```
/organizations/:organization_id/events/:event_id/event_questions/:event_question_id/answers
```

**Custom Actions for Real-time Features**:
```ruby
# Facilitator broadcasts question to all participants
POST /api/organizations/1/events/2/event_questions/3/broadcast_event_question

# Participant submits answer with real-time notification
POST /api/organizations/1/events/2/event_questions/3/answers/4/broadcast_answer
```

### Template Method Pattern Implementation

**Base Controller Structure**:
```ruby
class BaseController < ApplicationController
  include ResourceFindable
  
  def index
    resources = find_resources
    render json: filter_and_paginate(resources)
  end
  
  protected
  
  def find_resources
    # Template method - override in subclasses
    raise NotImplementedError
  end
end
```

**Concrete Implementation**:
```ruby
class AnswersController < BaseController
  setup_resource_finder
  self.finder_resource_name = :answer
  
  protected
  
  def find_resources
    find_answer # Automatically validates: organization → event → event_question → answer
  end
end
```

## Testing Strategy

### Backend Testing (RSpec)
- **Unit Tests**: Model validations, associations, business logic
- **Integration Tests**: API endpoints with authentication and authorization
- **System Tests**: End-to-end QR code flows and real-time messaging

### Frontend Testing (React Testing Library)
- **Component Tests**: Individual React component behaviour
- **Integration Tests**: User flow testing with mocked API responses
- **E2E Tests**: Full application workflows including real-time features

### Test Coverage Goals
- **Backend**: 95%+ line coverage with focus on critical business logic
- **Frontend**: 90%+ component coverage with emphasis on user interactions

## Performance Considerations

### Database Optimisation
- **Indexing Strategy**: Composite indexes on frequently queried resource hierarchies
- **Query Optimisation**: Eager loading for nested resource relationships
- **Connection Pooling**: Configured for concurrent real-time usage

### Real-time Scalability
- **Ably Scaling**: Utilises Ably's global edge network for low-latency delivery
- **Channel Management**: Automatic cleanup of inactive event channels
- **Message Persistence**: Configurable retention for offline participant catch-up

### Frontend Performance
- **Progressive Web App**: Enables offline capabilities and fast loading
- **Component Lazy Loading**: Reduces initial bundle size
- **Optimistic Updates**: Immediate UI feedback with server reconciliation

## Security Implementation

### Authentication & Authorization
- **Session Management**: UUID-based tokens with configurable expiration
- **Resource Isolation**: Multi-tenant architecture prevents cross-organization access
- **Role-based Permissions**: Granular control at organization and event levels

### Data Protection
- **Input Validation**: Comprehensive sanitisation of all user inputs
- **SQL Injection Prevention**: Parameterised queries and ORM usage
- **CORS Configuration**: Restricted cross-origin access for API endpoints

### Privacy Considerations
- **Anonymous Participation**: UUID-based identity without personal data requirements
- **Data Retention**: Configurable retention policies for response data
- **Consent Management**: Built-in consent workflows for data collection

## Deployment Architecture

### Current Setup (Heroku)
- **Application Servers**: Horizontally scalable dynos
- **Database**: PostgreSQL with automated backups
- **Asset Delivery**: Integrated CDN for static assets
- **Monitoring**: Application performance monitoring and error tracking

### Production Considerations
- **Load Balancing**: Application-level load distribution
- **Database Scaling**: Read replicas for analytics queries
- **Caching Strategy**: Redis for session storage and query caching
- **Backup Strategy**: Automated daily backups with point-in-time recovery

## Migration Strategy: Rails to Django

### Technical Approach
1. **Schema Preservation**: Maintain exact PostgreSQL schema structure
2. **API Compatibility**: Ensure frontend continues working during transition
3. **Feature Parity**: Complete Rails feature implementation in Django
4. **Data Migration**: Zero-downtime database transition strategy
5. **Testing**: Parallel testing environments for validation

### Migration Benefits
- **Team Expertise**: Alignment with team's Django experience
- **Ecosystem**: Better Python ML/AI library integration
- **Scalability**: Django's mature ecosystem for production deployment
- **Maintenance**: Long-term codebase maintainability improvements

---

*For AI integration architecture details, see [AI Integration Roadmap](ai-integrations.md)*

*For product strategy and user research, see [Product Strategy](product-strategy.md)*
