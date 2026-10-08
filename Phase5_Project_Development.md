# 5. Project Development Phase

*Phase 5*

### Development Flow

- The user registers or logs in, opens the home page and chooses a planner (Home, Party or Jewelry).
- The user fills the form with budget and preferences; the Jewelry form also accepts an outfit image.
- Submitting the form sends a POST request to the matching FastAPI endpoint.
- The service layer builds a prompt and calls Gemini 1.5 Flash Pro, then links the result to platforms such as Amazon, Flipkart, IKEA, Swiggy, Zomato and OYO.
- The response is formatted into structured recommendations and saved to the user’s history.
- Results appear as card-like layouts on the recommendations page.

### Core Functions

| Module | Description |
|---|---|
| Home Planner | Takes the budget, room types and quantities and recommends cost-effective furniture, decor and lighting balanced across function, style and price |
| Party Planner | Splits the budget across catering, decoration and entertainment, adds venue and stay options, and tailors the plan to the event type using conditions |
| Jewelry Planner | Takes budget, occasion, style and optional outfit image and returns matching jewelry options |
| Authentication & Session | /register, /login, /logout, /token (JWT), /session-info and /session-data for personalized access |
| History | /history stores and shows previous queries and results for review or re-use |

### Frontend Pages

- **Home Page** – landing page introducing the features with links to the planners.
- **Testimonials Page** – user reviews and success stories.
- **Register / Login Pages** – account creation and authentication.
- **User Dashboard** – recent recommendations, saved queries and personalized insights.
- **Planner and Recommendation Pages** – an input page and a results page for each of Home Interior, Party and Jewelry.
- **Recommendation History Page** – log of past queries and results.

### Technology Stack

| Layer | Technology |
|---|---|
| Language / Framework | Python 3.10+, FastAPI, Uvicorn (ASGI server) |
| Templating / Frontend | Jinja2, HTML, CSS, JavaScript |
| AI | Google Gemini 1.5 Flash Pro (via API key) |
| Security | JWT tokens, session management, CORS, .env configuration |

### How to Run

```
pip install -r requirements.txt
# add your Gemini API key to the .env file
uvicorn main:app --reload
# open http://127.0.0.1:8000
```
