# 3. Project Design Phase

*Phase 3*

### System Architecture

PocketSmart AI has three main parts: the Frontend (HTML, CSS and Jinja2 templates), the Backend (FastAPI application) and the AI layer (Google Gemini 1.5 Flash Pro). The request flow is:

```
Browser (HTML form + CSS)
  -> FastAPI endpoints (main.py)
  -> Planner logic (gemini_utils.py: prompts, budget formatting, image analysis)
  -> Gemini 1.5 Flash Pro (cloud)
  -> Recommendation cards shown on the page
```

### Model Selection

| Model | Used For | Benefits |
|---|---|---|
| Gemini 1.5 Flash Pro (via API) | Budget understanding, image analysis, structured suggestions, platform-specific product recommendations for Home, Party and Jewelry | Multimodal (text + image), fast responses, structured outputs, cloud inference |

### Module Design

| Module | Responsibility |
|---|---|
| main.py | FastAPI app, endpoints, CORS, session handling, startup |
| gemini_utils.py | Prompt orchestration, budget formatting, domain segmentation, image analysis, fallback logic |
| routes/ | API endpoints |
| services/ | Recommendation logic and AI calls |
| models/ | Input and output schemas |
| templates / static | Jinja2 HTML pages and CSS styling |
| .env | Gemini API key and configuration |

### API Endpoint Design

| Endpoint | Purpose |
|---|---|
| /generate-home | Home interior recommendations (furniture, decor, lighting) |
| /generate-party | Catering, venue and decoration options for events |
| /generate-jewelry | Text + image input to return style-matched jewelry |
| /register, /login, /logout | User registration, authentication and session end |
| /token | Issues a JWT token after successful authentication |
| /session-info, /session-data | Session metadata and session-specific data for personalization |
| /recommendations-details | Detailed AI recommendations by budget, preferences and category |
| /history | User’s past recommendation queries and results |

### AI Design

- Gemini receives a structured prompt for each planner (home, party or jewelry) containing the budget, preferences and platform list.
- For the Jewelry Planner the outfit image is sent together with the text prompt for colour and style analysis.
- Prompts are tuned for budget interpretation so that the suggested items stay within the entered budget.
- Errors are handled safely, and default recommendations are returned if the AI result is insufficient.
