# Sentinel-M6: Tech Health Agent
**Description:** An automated node for Utopia OS that cross-references Linear task completion with GitHub commit velocity to detect "Progress Drift" in M1 fellows.

### How to Run
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Add your API keys to the `CONFIGURATION` section in `main.py`.
4. Update `registry.json` with target fellow data.
5. Execute: `python main.py`.

### Prompt Used
"You are a Tech Lead. Analyze these signals and return a JSON object. Signals: GitHub Commits={commits}, Linear Done={done}/{total}. Return format: {"score": 1-10, "summary": "string", "action": "string"}"

### Tools & APIs Called
* **Linear GraphQL API:** To fetch workspace issues and project status.
* **GitHub REST API:** To audit repository commit history.
* **Google Gemini 1.5 Flash:** For risk reasoning (via fallback-ready REST integration).
