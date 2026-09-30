# Hi, I'm Anusree 👋

**QA Automation Engineer**: I build test automation for web UIs, REST APIs and Android apps with Python, Playwright, Appium and pytest, test APIs with Postman and Newman, and performance-test them with Apache JMeter. I use AI-assisted workflows (my own reusable Claude Code skills) to design and generate them, and I review and verify every result.

## 🧪 Featured projects

### [Mobile Test Automation: My Demo App (Android)](https://github.com/Anusreepsuresh074/mydemoapp-mobile-automation)
![Mobile tests](https://github.com/Anusreepsuresh074/mydemoapp-mobile-automation/actions/workflows/mobile-tests.yml/badge.svg) · **[Live report](https://anusreepsuresh074.github.io/mydemoapp-mobile-automation/)** · **[Test Summary Report](https://github.com/Anusreepsuresh074/mydemoapp-mobile-automation/blob/main/docs/test-summary-report.md)**

End-to-end tests for Sauce Labs' My Demo App, a native Android shopping app: catalogue, sorting, product, cart, sign-in, checkout and app state.

- **Appium 3 (UiAutomator2) + Python + pytest**, built with the **Page Object Model**
- **62 test cases** (28 positive, 18 negative, 16 edge), 43 of them found through six exploratory testing sessions; every locator confirmed on the running app; explicit waits only, no retries
- Found **8 real app defects**, including a crash and two security issues, tracked as strict xfails
- Environment health check before every run; Allure reports with screenshots and page source on failure
- CI on GitHub Actions on an **Android emulator** (Pixel 6, API 35, KVM): smoke on every push, full regression nightly

### [Performance Testing: DummyJSON e-commerce API](https://github.com/Anusreepsuresh074/ecommerce-performance-testing)
![Performance tests](https://github.com/Anusreepsuresh074/ecommerce-performance-testing/actions/workflows/perf.yml/badge.svg) · **[Live dashboards](https://anusreepsuresh074.github.io/ecommerce-performance-testing/)** · **[Test Summary Report](https://github.com/Anusreepsuresh074/ecommerce-performance-testing/blob/main/docs/test-summary-report.md)**

Load, stress and spike testing of a shopper journey (login, profile, browse, search, view product), following the full performance testing life cycle.

- **Apache JMeter 5.6.3**: correlation, parameterisation, assertions on every request, a reusable Test Fragment, property-driven load profiles
- A signed-off **Performance Test Plan**: NFRs, a workload model built with **Little's Law**, pacing and think time, entry/exit criteria
- **6 runs** (smoke, baseline, load ×2, stress, spike): every SLA met, p90 under 0.8 s at 2.5× normal load
- Script validated offline against a local stub server (37 automated checks) before touching the real API
- **Test Summary Report** with observations and recommendations; CI on GitHub Actions, with HTML dashboards on GitHub Pages

### [API Test Automation: DummyJSON (JWT auth)](https://github.com/Anusreepsuresh074/ecommerce-api-automation)
![CI](https://github.com/Anusreepsuresh074/ecommerce-api-automation/actions/workflows/ci.yml/badge.svg) · **[Live report](https://anusreepsuresh074.github.io/ecommerce-api-automation/)**

An API suite for a fake e-commerce API with a real JWT login, refresh and expiry flow.

- **Python + requests + pytest**, **91 tests** from 75 reviewed test cases
- The full **token lifecycle**, tested for real: login, JWT claims, actual expiry (401), refresh
- **JSON Schema** checks on every response, down to every nested product review
- Found **13 real defects**, including sensitive data exposure and token misuse, tracked as strict xfails
- Credentials redacted from all logs and reports; parallel runs; Allure; CI on GitHub Actions

### [API Testing with Postman + Newman: DummyJSON](https://github.com/Anusreepsuresh074/dummyjson-postman-newman)
![API tests](https://github.com/Anusreepsuresh074/dummyjson-postman-newman/actions/workflows/newman.yml/badge.svg) · **[Live reports](https://anusreepsuresh074.github.io/dummyjson-postman-newman/)**

A Postman collection for the same JWT-protected API, run from the command line and in CI with Newman.

- **61 requests** from a reviewed test case matrix: auth, products, search, categories, simulated writes, protected routes
- `pm.test` assertions, **JSON Schema** checks, token **chaining** through variables, collection-level shared checks
- **Data-driven** search from a CSV file; read-your-write checks proving writes are simulated
- The **same 13 defects**, re-confirmed in Postman and kept visible in a non-gating folder; credentials only at run time, every report scanned for leaks
- CI on GitHub Actions: static checks → gating and non-gating Newman runs → HTML reports on GitHub Pages; nightly schedule

### [UI Test Automation: automationexercise.com](https://github.com/Anusreepsuresh074/automationexercise-ui-tests-eCommerce)
![UI Tests](https://github.com/Anusreepsuresh074/automationexercise-ui-tests-eCommerce/actions/workflows/ui-tests.yml/badge.svg) · **[Live report](https://anusreepsuresh074.github.io/automationexercise-ui-tests-eCommerce/)** · **[Test Summary Report](https://github.com/Anusreepsuresh074/automationexercise-ui-tests-eCommerce/blob/main/docs/test-summary-report.md)**

End-to-end tests for an e-commerce site: browse, search, cart, signup/login, checkout, contact form and accessibility.

- **Playwright (Python) + pytest**, Page Object Model with reusable components
- **58 tests × 3 browsers** (Chromium, Firefox, WebKit), run in parallel, fully isolated per test
- API-backed test data setup and cleanup; automated **axe-core accessibility** scans
- Found **5 real site defects**, tracked as strict xfails
- CI on GitHub Actions: lint + type checks → smoke on every push → nightly regression → Allure report on GitHub Pages; Docker image, Dependabot

### [API Test Automation: Restful-Booker](https://github.com/Anusreepsuresh074/restful-booker-api-automation)
![CI](https://github.com/Anusreepsuresh074/restful-booker-api-automation/actions/workflows/ci.yml/badge.svg) · **[Live report](https://anusreepsuresh074.github.io/restful-booker-api-automation/)**

A hotel-booking REST API suite covering all 8 endpoints.

- **Python + requests + pytest**, Service/API Object Model
- **29 tests**: happy path, negative, boundary, auth/authz and **JSON Schema contract** checks
- **Read-your-write verification**: every write is confirmed with a follow-up read
- Parallel runs, retries for transient network errors, Allure reporting, CI on GitHub Actions

### [AI Test Generation: QA Script Generator](https://github.com/Anusreepsuresh074/QA-Script-Generator)

A study project on AI agents, built with two teammates: it reads a Jira ticket and the API's spec, and an LLM turns the acceptance criteria into test scenarios and runnable test scripts.

- **Python + FastAPI**, with **Ollama** as the main LLM and **Groq** as the backup, plus retries and a quality filter on weak scenarios
- Matches each acceptance criterion to an endpoint by keyword, embedding (sentence-transformers) or LLM scoring
- My part: support for **GraphQL, SOAP, gRPC and WebSocket** specs (a parser factory), and **Robot Framework, Jest and Postman** output beside Pytest
- Also mine: a **Slack-to-Jira bug agent** that decides which messages are real QA issues and files tickets
- An **offline demo** (fake Jira, a mock Customers API, a local model) that showed why AI-written tests must be run and reviewed before they are trusted

## 🛠️ Toolbox

`Python` · `Playwright` · `Appium` · `pytest` · `requests` · `Postman` · `Newman` · `Apache JMeter` · `JSON Schema` · `Allure` · `GitHub Actions` · `GitHub Pages` · `Docker` · `ruff` · `mypy` · `axe-core` · `Claude Code`

**Practices:** Page Object Model · mobile testing on Android emulators · test design (happy / negative / boundary / auth / a11y) · traceable test-case matrices · performance test planning (NFRs, workload models, SLAs) · load / stress / spike testing · result analysis and reporting · CI/CD · parallel & cross-browser testing · flaky-test root-causing

## 📫 Contact

📧 [anusreepsuresh074@gmail.com](mailto:anusreepsuresh074@gmail.com) · 💼 [LinkedIn](https://www.linkedin.com/in/anusree-p-671700184)
