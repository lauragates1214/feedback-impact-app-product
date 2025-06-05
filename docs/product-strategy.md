# Product Strategy and User Research

## Product Vision

**Mission**: To make it easy for organizations to collect the valuable feedback that usually slips through the cracks.

**Vision**: Make real-time feedback as natural and fluid as conversation—intuitive, human, and even joyful. At the same time, Obwob is built to be rock-solid beneath the surface: a tool you can trust to capture and securely hold fleeting, vital insights that might otherwise be lost.

## The Problem We're Solving

### The Feedback Gap

Have you ever wondered what happens to the feedback forms you're asked to fill out after an event? The answer is: not much.

This isn't because organizations don't need the feedback—they desperately do. Feedback means the difference between securing funding and losing it, between improving services and stagnating, between understanding impact and guessing. In organizations that rely on funding, it's the evidence needed for grant renewals. In healthcare training, it shapes how professionals are equipped to work with patients. In academic research, it determines which projects continue and which end, demonstrates the impact needed to secure institutional funding, and drives academic prestige.

### The Scale of the Problem

Traditional feedback methods simply don't work:

- **Educational settings: Published averages show 44.1% response rates (Wu et al 2022), though real-world experience often falls well below this
- **Events and conferences: Reported completion rates of 10-20%, with many organizations experiencing single-digit percentages
- **Community organizations: Studies suggest 13-16% response rates, but stakeholder feedback indicates 5-10% is more typical

Even more critically, post-event feedback captures only faded memories—the spontaneous insights, emotional responses, and valuable revelations experienced during the event have already slipped away as participants head off to their next engagement.

### The Real Impact

This means organizations are making decisions, writing reports and bids, and submitting impact findings based on feedback from just a tiny fraction of participants—and even that feedback is diluted by time and distance from the actual experience. The valuable insights, in-the-moment reactions, creative ideas, and transformative realizations from the other 80-95% of participants? Lost forever.

Research shows that 77% of users prefer organizations that ask for their feedback (ConstantContact), but traditional methods make it difficult to respond in the moment when insights are most valuable.

## Research Foundation

### Origins in Vulnerable Population Research

Obwob emerged from Dr Purcell-Gates's Objects Without Borders research project, which revealed a critical insight while working with vulnerable populations including refugees and low-income communities: despite various technological barriers, smartphones were consistently the most accessible technology.

**Key Research Findings**:
- Traditional feedback methods (paper forms, post-event surveys) had extremely low completion rates
- Digital tools requiring downloads or accounts created insurmountable barriers
- Smartphones were universally accessible regardless of other technology limitations
- Real-time feedback collection captured insights that disappeared in post-event methods
- Participants valued having ownership of their own responses for personal reflection

### User Research Insights

**Primary Pain Points Identified**:
1. **Timing Mismatch**: Post-event feedback misses in-the-moment insights
2. **Technical Friction**: Downloads and sign-ups create abandonment
3. **Administrative Burden**: Organizations lack resources for complex feedback systems
4. **Data Usability**: Collected feedback often unusable for reporting or funding applications
5. **Participant Engagement**: Traditional methods feel extractive rather than collaborative

**User Behaviour Patterns**:
- High smartphone ownership across all demographics studied
- Immediate willingness to scan QR codes vs. resistance to app downloads
- Higher quality responses when collected in real-time vs. retrospectively
- Deeper engagement with and increased reported enjoyment of event when using real-time feedback collection
- Strong preference for anonymous participation in sensitive contexts
- Desire for personal access to own responses for continued reflection

## Target Market Analysis

### Primary Markets

**1. Higher Education & Research**
- **Need**: Research impact evidence for REF submissions and grant applications
- **Pain Points**: Manual data collection, poor response rates, administrative overhead
- **Opportunity**: 165 UK universities, growing emphasis on public engagement measurement

**2. Healthcare & Professional Development**  
- **Need**: Training effectiveness measurement and reflection documentation
- **Pain Points**: Limited time for feedback collection, need for evidence-based practice
- **Opportunity**: NHS trusts, private healthcare, professional development organizations

**3. Arts & Cultural Organizations**
- **Need**: Impact evidence for funding applications and stakeholder reporting
- **Pain Points**: Resource constraints, difficulty capturing audience engagement
- **Opportunity**: Arts Council England funding requirements, 4,500+ arts organizations

**4. Museums & Heritage Organizations**
- **Need**: Visitor engagement evidence and exhibition effectiveness measurement
- **Pain Points**: Capturing authentic visitor experience without disrupting flow
- **Opportunity**: Public engagement requirements, visitor experience optimization

**5. Community & Third Sector Organizations**
- **Need**: Program effectiveness documentation and participant voice capture
- **Pain Points**: Limited technical resources, need for inclusive feedback methods
- **Opportunity**: 180,000+ registered charities, increasing focus on impact measurement

### Market Sizing

**Total Addressable Market (TAM)**: Organizations requiring feedback collection across education, healthcare, arts, and community sectors (~£2.8B globally)

**Serviceable Available Market (SAM)**: UK organizations needing real-time feedback tools (~£180M)

**Serviceable Obtainable Market (SOM)**: Early adopter organizations prioritizing inclusive feedback (~£18M over 3 years)

## Competitive Analysis

### Direct Competitors
- **Mentimeter, Slido, Poll Everywhere**: Presentation-focused, business audiences
- **SurveyMonkey, Typeform**: Limited real-time functionality compared to live environment needs
- **Pigeonhole Live**: Event Q&A, limited feedback depth

### Competitive Advantages

**1. Purpose-Built for Live Environments**
- Designed for dynamic, messy, real-world settings vs. controlled presentation environments
- Mobile-first approach vs. laptop/desktop assumptions
- Frictionless access vs. account-based systems

**2. Lightweight Engagement **
- Single focus on feedback collection vs. feature-bloated platforms
- Fast, lightweight deployment vs. complex setup requirements
- Built-in analytics vs. premium add-ons

**3. Inclusive by Design**
- Research-backed approach to vulnerable population engagement
- Anonymous participation options vs. required identification
- Accessibility-first architecture vs. retrofitted solutions

**4. Data Ownership and Structure**
- Participant access to own responses vs. organization-only data
- Export-ready formatting vs. platform lock-in
- Contextual linking vs. isolated response collection

### Key Positioning Statement

*"I'm not aware of anything like this in this space – an incredibly lightweight way to capture feedback during events."* - Jason Milgram, Early Tester

## Product Development Strategy

### Development Phases

**Phase 1: MVP Foundation (Summer 2025 - January 2026)**
- Complete Django migration from Rails prototype
- Core real-time feedback functionality
- QR code access system with optional account creation
- Basic analytics and export capabilities
- Organization and event management dashboard

**Phase 2: Strategic Testing & Validation (January - June 2026)**
- Bath Spa University integration for REF PCE data collection
- Pilot testing with diverse sector partners
- Enhanced facilitator dashboard and real-time response viewing
- Case study development across sectors

**Phase 3: Intelligence Layer (Mid-2026)**
- AI-powered response summarization
- Sentiment analysis and thematic clustering
- Multi-language support
- Advanced analytics and reporting

**Phase 4: Advanced Features (2027+)**
- Voice and image response capabilities
- Predictive insights and recommendations
- Advanced integration capabilities
- White-label solutions

### Feature Prioritization Framework

**1. Impact vs. Effort Matrix**
- **High Impact, Low Effort**: QR code access, basic analytics
- **High Impact, High Effort**: AI integration, multi-modal responses
- **Low Impact, Low Effort**: UI polish, minor feature additions
- **Low Impact, High Effort**: Advanced integrations, enterprise features

**2. User Value Prioritization**
- **Must-Have**: Frictionless participation, real-time collection
- **Should-Have**: Analytics, export capabilities, facilitator tools
- **Could-Have**: Advanced AI features, voice responses
- **Won't-Have**: Complex integrations, presentation tools

## Go-to-Market Strategy

### Development and Launch Timeline

**Phase 1: Pilot Program (Current)
- Working with 2 arts organizations in UK and Prague
- Gathering usage data and refinement feedback
- Building case studies and testimonials

**Phase 2: MVP Development (Summer 2025 - January 2026)**
- Complete Django migration and core feature development
- Continued testing with existing pilot partners

**Phase 3: Strategic Testing & Validation (January - June 2026)**
- **Bath Spa University Integration**: Testing with researchers and research projects to collect PCE data for REF submissions
- **Pilot Testing Partners**: Early adopter customers across arts organizations, healthcare charities, public & third sector organizations, and university researchers at introductory rates
- **Case Study Development**: Building evidence base for market launch across diverse sectors

**Three-Pronged Partnership Strategy:**
1. **Pilot Testing Partners**: Early adopter customers providing real-world feedback on functionality and user experience while representing diverse sectors to validate market fit
2. **Market Research Collaborators**: Organizations helping identify and connect with new potential sectors while validating business model across different industries  
3. **Strategic Distribution Partners**: Exploring collaboration with Jisc for UK higher education market; seeking additional partners for other sectors to help with marketing, sales, customer support, and scaling reach

**Phase 4: Market Launch (Mid-2026+)**
- Leverage case studies and validation data for broader market penetration
- International expansion starting with English-speaking markets
- Scale through established distribution partnerships

### Strategic Focus Areas

**Building User Base:**
- Validating identified sectors to confirm market viability
- Discovering and testing potential new sectors not yet identified

**Product Development:**
- Advancing from current early test version to robust MVP
- Refining based on real-world feedback and use cases

**Business Model Validation:**
- Testing pricing structures and partnership models
- Establishing scalable support frameworks

## Brand Positioning

### Brand Values
- **Simplicity and Efficiency**: Technology that gets out of the way
- **Strength and Reliability**: Dependable performance in any environment
- **Accessibility for All**: Inclusive design with no technical barriers
- **Ethical Engagement**: Built-in consent and participant ownership

### Value Proposition

**For Organizations**: "Catch feedback before it slips away" - Transform fleeting insights into structured data for reports, funding bids, and strategic decisions.

**For Participants**: Anonymous, immediate feedback that you can revisit for personal reflection and continued engagement.

**For Facilitators**: Lightweight tool that works in real-world environments without technical overhead or administrative burden.

### Messaging Framework

**Primary Message**: Real-time feedback collection that captures insights traditional methods miss

**Supporting Messages**:
- No downloads, no friction—just scan and respond
- Built for messy, dynamic environments where feedback matters most  
- Transform momentary insights into lasting evidence
- Designed with vulnerable populations in mind, accessible to all

### Unique Selling Proposition

Think of Obwob as a powerful magnet for feedback—drawing in those valuable thoughts and reactions that would otherwise scatter and disappear. Just as a magnet effortlessly pulls metal objects toward itself, Obwob attracts responses through a simple QR code scan. When facilitators push a question, it's like activating the magnetic field. Thoughts that might have remained unspoken are drawn in, captured, and securely held. No insight slips away.

## Success Metrics

### Product Metrics
- **Engagement**: Response rates per event (target: 75-90% vs. traditional 5-15%), time-to-first-response
- **Usage**: Events per organization, questions per event, retention rates
- **Quality**: Response length and depth, facilitator satisfaction scores

### Business Metrics
- **Growth**: Monthly active organizations, user acquisition cost
- **Revenue**: Annual recurring revenue, customer lifetime value
- **Market**: Market share in target sectors, competitive win rate

### Impact Metrics
- **Research**: Papers published using Obwob data, funding secured through impact evidence
- **Healthcare**: Training programs improved, patient outcomes influenced
- **Community**: Participant voices amplified, program effectiveness demonstrated
- **Academic**: REF submissions supported, public engagement evidence captured

### Early Results from Pilot Programs

**Quantitative Outcomes:**
- Traditional post-event forms: 5-15% completion rate
- Obwob real-time collection: 90-100% participation rate
- Administrative overhead: Eliminated need for manual data entry and chasing responses
- Data structure: Responses automatically formatted for analysis and reporting

**Qualitative Feedback:**
- *"Obwob is a game-changer because it enables us to capture feedback that typically slips away"* - UK Arts Organization
- *"Makes the feedback process more inclusive and meaningful, engaging participants rather than simply extracting data from them"* - Prague University Research Institute

## Team Credentials and Vision

### Founder Background

Creator and Lead Developer Laura Gates brings unique qualifications combining academic research excellence with technical development expertise. Together with her academic work as Dr Purcell-Gates, she has: 
- **Research Excellence**: 4* REF Impact Case Study demonstrating public engagement effectiveness—the same analog methods now being coded into Obwob
- **Technical Expertise**: Full-stack development experience with sophisticated system architecture
- **Domain Knowledge**: Deep understanding of helping professions where organizations are stretched for resources but need robust, ethical data
- **Interdisciplinary Approach**: Background in theatre and puppetry informing understanding of how objects, narrative, and world-building can open new ways of engaging and connecting

### Vision Statement

Our vision is to make real-time feedback as natural and fluid as conversation—intuitive, human, and even joyful. We want Obwob to become the go-to tool for facilitators across sectors—lightweight enough to stay out of the way, nimble enough to respond in real time, and strong enough to securely transform fleeting feedback into actionable data.

---

*For technical implementation details, see [Technical Architecture](technical-architecture.md)*

*For AI integration roadmap, see [AI Integration Plans](ai-integrations.md)*

*For brand strategy details, see [Brand Strategy](brand-strategy.md)*

*For current pilot results and case studies, see [Case Studies](case-studies.md)*
