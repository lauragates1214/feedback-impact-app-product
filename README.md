# obwob-product
Real-time feedback collection platform - product documentation, technical architecture, and development strategy.


# Overview
Obwob transforms traditionally fleeting, difficult-to-capture feedback into valuable, structured data that supports impact reports, research and funding bids without the administrative overhead of traditional methods.

Built as a mobile-first Progressive Web App, Obwob enables facilitators to instantly connect with participants during events and gather their responses in real-time through participants' own mobile phones—with no downloads, logins, or technical barriers.


# The Problem We're Solving
Traditional feedback collection fails in live environments:
- Post-event forms get poor response rates
- Paper surveys interrupt the flow of activities
- Digital tools require downloads and setup that create friction
- Valuable insights are lost in the moment they occur

Obwob emerged from research with vulnerable populations (refugees, low-income communities) where smartphones were consistently the most accessible technology, despite various other barriers.


# Key Technical Achievements
Sophisticated Resource Hierarchy Management
- Custom-built recursive authentication system that dynamically validates nested resource relationships (Organizations → Events → Questions → Answers) using Template Method design pattern and metaprogramming.

Real-time Communication Architecture
- Ably-powered live messaging system enabling instant question pushing and response collection across multiple participant devices simultaneously.

Progressive Migration Strategy
- Currently transitioning from Rails prototype to production Django backend while maintaining full functionality—demonstrating practical experience with complex system migrations.

AI Integration Planning
- Architected for intelligent features including response summarisation, sentiment analysis, and thematic clustering using RAG (Retrieval-Augmented Generation) and MCP (Model Context Protocol) approaches.

Frictionless User Experience
- QR code-based access system that creates anonymous users with UUIDs, enabling immediate participation without downloads or account creation.


# Current Development Status
Working Demo Features:
- Complete facilitator and participant event access via QR codes
- Live question broadcasting and response submission
- Asynchronous question answering capabilities
- Welcome and confirmation user flows
- Full backend API with comprehensive test coverage

In Development (Django Migration):
- Organization event dashboard and question bank management
- Real-time response viewing for facilitators
- Advanced analytics and export functionality
- Multi-language support and voice/image submissions


# Technical Architecture
Backend
- Current: Rails 8.0 with PostgreSQL
- Production: Django with PostgreSQL (migration Q2 2025)
- Real-time: Ably channels for live messaging
- Authentication: UUID-based anonymous users with hierarchical resource validation
- Testing: Comprehensive RSpec test suite with unit and integration coverage

Frontend
- Framework: React with Progressive Web App capabilities
- Styling: SCSS with component-based architecture
- Testing: React Testing Library (in development)
- Real-time: Ably client integration

Database Design
Sophisticated relational structure supporting:
- Multi-tenant organizations with role-based access
- Flexible event and question management
- Trackable response collection with contextual linking
- Soft deletion and audit trails throughout

Deployment
- Platform: Heroku
- Monitoring: Application performance tracking
- Scaling: Designed for horizontal scaling with database optimisation


# AI Integration Roadmap
MVP-Ready Features
- Smart Response Summarisation: LLM-generated summaries of participant feedback
- Sentiment Analysis: Automated emotional tone detection across responses
- Thematic Clustering: Automatic grouping of similar feedback using embeddings
- Question Enhancement: AI-assisted question improvement suggestions

Future Development
Facilitator Copilot: Real-time insights and suggestions during events
Adaptive Follow-ups: Context-aware question recommendations
Voice Transcription: Whisper integration for audio responses


# Target Markets
Higher Education: Research impact evidence collection and academic event feedback
Healthcare: Training evaluation and professional development assessment
Arts Organizations: Community engagement documentation for funding applications
Community Organizations: Program effectiveness measurement and participant voice capture
Museum & heritage sites
Additional market research in progress 2025-26


# Development Approach
Methodology: Agile sprints with iterative client feedback
Timeline to date: 6 months planning + 6 months initial development
Testing: Test-driven development with comprehensive coverage
Client Collaboration: Currently piloting with UK and Prague-based partner organizations


# Repository Contents
This repository contains comprehensive product documentation including:
- Technical Architecture: Detailed system design and implementation patterns
- User Research: Findings from work with vulnerable populations
- Product Strategy: Market positioning and competitive analysis
- Brand Strategy: Complete visual identity and messaging framework
- AI Integration Plans: Detailed roadmap for intelligent features

For technical implementation details, see Technical Architecture
For product strategy and market research, see Product Strategy
For AI integration plans, see AI Integration Roadmap
