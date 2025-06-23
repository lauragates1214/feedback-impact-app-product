**Real-time feedback collection that captures insights before they slip away.**<br>
**Creator and Lead Developer: Laura Gates**<br>
**Currently in development at Bath Spa University as part of ongoing research into inclusive feedback collection, impact and engagement methods.**


[![Status](https://img.shields.io/badge/status-active%20development-green)]()
[![Tech Stack](https://img.shields.io/badge/stack-React%20%7C%20Django%20%7C%20PostgreSQL-blue)]()
[![Testing](https://img.shields.io/badge/testing-RSpec%20%7C%20React%20Testing-brightgreen)]()

# Overview
This app transforms fleeting, hard-to-capture feedback into structured data that supports impact reporting, research and funding applications, without the administrative overhead of traditional methods.

Designed as a mobile-first progressive web app, it enables facilitators to connect instantly with participants during live events. Participants respond via their own mobile devices, with no downloads, logins or technical friction required.


# The Problem
Traditional feedback collection fails in live environments:
- Post-event forms yield poor response rates
- Paper forms disrupt event flow
- Download-heavy digital tools create barriers
- Valuable insights get lost before they can be captured

Our research, especially with vulnerable groups (refugees, low-income communities), showed smartphones as the most accessible tech despite multiple barriers, informing the design of this frictionless solution.


# Key Technical Features
**Resource Hierarchy Management:** Recursive, metaprogrammed authentication validating nested resources (Organizations → Events → Questions → Answers)
**Real-time Messaging:** Powered by Ably for instantaneous question pushing and response collection across multiple devices
**Progressive Migration:** Transitioning from Rails prototype to production-ready Django backend while maintaining full functionality
**AI Integration Planning:** Architected for advanced features like response summarisation, sentiment analysis, and thematic clustering via Retrieval-Augmented Generation
**Frictionless UX:** QR code access creates anonymous users with UUIDs; no account creation or downloads required


# Current Development Status
Working Demo:
- Facilitator and participant event access via QR codes
- Live question broadcasting and response submission
- Asynchronous answering
- User flow for event welcome and confirmation
- Fully tested backend API

In Progress (Django Migration):
- Organization event dashboards and question bank management
- Real-time facilitator response viewing
- Advanced analytics and export tools
- Multi-language, voice, and image submission support
- Optional persistent user accounts


# Technical Architecture
Backend
- Prototype: Rails 8.0 with PostgreSQL
- Production: Django + PostgreSQL (Q2 2025)
- Real-time: Ably channels
- Authentication: UUID anonymous users with hierarchical validation
- Testing: RSpec unit and integration coverage

Frontend
- React PWA
- SCSS styling
- React Testing Library (in development)
- Ably client integration

Database 
- Multi-tenant support with role-based access
- Event and question management
- Trackable, contextual response collection
- Soft deletion and audit trails 

Deployment
- Heroku
- Performance monitoring
- Horizontal scaling ready


# AI Integration Roadmap
**MVP:** Response summarisation, sentiment analysis, thematic clustering, AI-assisted question enhancement
**Future:** Facilitator Copilot (real-time insights), adaptive follow-ups, voice transcription


# Target Markets
Higher Education (impact evidence, event feedback)
Healthcare (training and assessment)
Arts Organizations (community engagement, funding)
Community Groups (program evaluation, participant voice)
Museums and Heritage Sites
Additional market research in progress 2025-26


# Development Approach
Agile sprints with iterative feedback
6 months planning + 6 months development
Test-driven development
Pilot partnerships in the UK and Czech Republic; in-development partnerships in Jordan, US, Zimbabwe and Namibia.


# Repository Contents
Technical architecture and design patterns
User research findings
Product and brand strategy
AI roadmap

## Legal Notice
Developed as part of Dr Laura Purcell-Gates’s role at Bath Spa University. IP belongs to Bath Spa University. Shared here with permission as a professional development portfolio.

GitHub username: **Laura Gates** (personal/professional name)  
Academic name: **Dr Laura Purcell-Gates**
