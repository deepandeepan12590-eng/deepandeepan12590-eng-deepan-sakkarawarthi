# 6. Project Testing Phase

*Phase 6*

### Test Approach

The application was run locally with Uvicorn and tested end to end through the browser at http://127.0.0.1:8000. Each planner was tried with varied budgets and preferences to confirm that the correct module is called, the recommendations stay within budget and the results appear on the page.

### Functional Test Cases

| No. | Test | Steps | Expected Result |
|---|---|---|---|
| 1 | Application loads | Open http://127.0.0.1:8000 | Home page with links to the planners is shown |
| 2 | Register and login | Create an account, then log in | User is authenticated and the dashboard opens |
| 3 | Home planner | Enter a budget, rooms and quantities | Cost-effective items from IKEA / Amazon within budget |
| 4 | Party planner | Enter budget, guests, event type, venue | Budget split across catering, decor and entertainment with Swiggy / Zomato / OYO options |
| 5 | Jewelry planner | Enter budget, occasion, style; upload an outfit image | Matching jewelry from Amazon / Flipkart |
| 6 | History | Open the history page | Past queries and results are listed |
| 7 | Logout | Click logout | Session ends and the login page opens |
| 8 | Error handling | Use an invalid API key or empty input | A helpful error message or fallback result is shown without crashing |

### Manual Testing Checklist

**Input and Generation**

- [ ] Home, Party and Jewelry forms accept budgets and preferences.
- [ ] Jewelry form accepts an optional outfit image.
- [ ] Each planner returns recommendations as cards.

**Quality and Accounts**

- [ ] Suggestions respect the entered budget and the right platforms.
- [ ] Register, login, logout and history work correctly.

**Errors and Interface**

- [ ] Missing or invalid API key produces a handled error message.
- [ ] Layout is responsive and readable on different screen sizes.
