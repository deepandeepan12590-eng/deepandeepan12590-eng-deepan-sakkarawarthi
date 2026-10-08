# 4. Project Planning Phase

*Phase 4*

### Milestones

| Milestone | Title | Activities |
|---|---|---|
| Milestone 1 | Gemini AI Initialization | Create Google Cloud account, enable the Gemini API, create and copy the API key; validate connectivity with text-only and image + text prompts |
| Milestone 2 | Core Functionalities Development | Initialize FastAPI, import libraries, load .env; build /generate-home, /generate-party, /generate-jewelry; add login, register and logout routes; session endpoints |
| Milestone 3 | Backend – FastAPI Integration (main.py) | Define routes, modular architecture, /recommendations-details, CORS and static routing, /history, startup and main function |
| Milestone 4 | UI Development | Build home, testimonials, register, login, dashboard, planner, recommendation and history pages with HTML, CSS and Jinja2 |
| Milestone 5 | Testing & Optimization | Test real-world budgets across all planners; refine prompts, session handling and UI/UX |

### Team Details

| Role | Name |
|---|---|
| Team Leader | T Deepan Sakkarawarthi |
| Team Member | Boopathi D |
| Team Member | Guna S |
| Team Member | Yashvanth Mamanivasan |
| Team Member | S Sakthivel |

### Deliverables

- Source code (FastAPI application with all modules)
- requirements.txt and .env template
- HTML templates and CSS stylesheet
- Screenshots of every page and feature in action
- Phase-wise project report (this document)

### Risks and Mitigation

| Risk | Mitigation |
|---|---|
| Accuracy of AI-generated recommendations | Continuous testing and refinement of prompt structures |
| Budget not respected in suggestions | Budget-adherence checks and prompt tuning; validation of inputs |
| Platform data accuracy | Simulated platform data with platform-accuracy evaluation during testing |
| Insufficient or empty AI results | Fallback and default recommendations |
| Data privacy and security | API key kept in .env; JWT authentication; secure credential storage |
