# 2. Requirement Analysis Phase

*Phase 2*

### Functional Requirements

- Provide a home page with links to the three planner modules and user actions.
- Provide planner forms for Home (budget, rooms, quantities), Party (budget, guests, event type, venue) and Jewelry (budget, occasion, style, optional outfit image).
- Generate budget-aware recommendations from Amazon, Flipkart, IKEA, Swiggy, Zomato, OYO and similar platforms using Gemini 1.5 Flash Pro.
- Analyze an uploaded outfit image together with text input (multimodal) for jewelry matching.
- Support registration, login, logout and JWT token-based access to protected routes.
- Store session data and show a dashboard and recommendation history for each user.
- Display the results in clean, card-like layouts with product names, details and prices.

### Non-Functional Requirements

- Lightweight, responsive interface built with HTML, CSS and Jinja2 templates.
- Modular backend with separate routes, services and models, so features can be upgraded easily.
- Gemini API key stored in a .env file and never shared in the code.
- Secure authentication and session handling; CORS configured for frontend communication.
- Input validation and fallback recommendations when the AI returns insufficient results.
- Graceful error handling with clear messages.

### Inputs and Outputs

| Feature | Input | Output |
|---|---|---|
| Home Planner | Budget, room types, item quantities | Cost-effective furniture, decor and lighting options per category |
| Party Planner | Budget, guest count, event type, venue details | Budget split across catering, decoration, entertainment and venue options |
| Jewelry Planner | Budget, occasion, style, optional outfit image | Style-matched jewelry options from shopping platforms |
| History | User session | Past queries and recommendations for review or re-use |

### Pre-requisites

| Requirement | Details |
|---|---|
| Python 3.10+ | Install from the official site, tick “Add Python to PATH”, verify with python --version |
| FastAPI | Backend framework (official docs and tutorials available) |
| Uvicorn | ASGI server; installed with pip install uvicorn |
| Jinja2 | HTML templating engine; installed with pip install jinja2 |
| HTML & CSS | Basic templating used in the templates and static folders |
| Gemini API Key | Sign in to Google Cloud / Google AI Studio, accept the terms, click “Get API key”, create the key, copy it and store it securely in the .env file |

### Assumptions and Constraints

- Cloud features need a valid Gemini API key and an internet connection.
- AI-generated suggestions depend on model output and may vary between runs.
- Third-party platform data is mocked or simulated in this version rather than fetched from live APIs.
