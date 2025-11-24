# 📅 AI Conference Tracker
A personal dashboard that tracks submission deadlines for major global AI and Computer Science (CS) conferences in real-time. Powered by data from ccfddl/ccf-deadlines.

# ✨ Key Features
* Accurate Deadline Calculation: Automatically parses various timezones like AoE (UTC-12) and UTC-8 to display deadlines in Korea Standard Time (KST).

* Intuitive Visualization:

  * CCF Rank Star Rating: CCF-A(★★★★), B(★★★☆), C(★★☆☆)

  * Urgency Indicators: Within 1 month (🔴 Red), Within 3 months (🟡 Yellow), Others (🟢 Green)

* Personalized Filters: Select only the conferences you want to see. Selection status is persisted even after restarting the browser (via Local Storage).

* Automatic Updates:

  * Automatically refreshes data every Saturday at 9:00 AM when the server is running.
* Rate Limit Protection: Includes API Rate Limit protection and local caching features.

* Raw Data Architecture: Preserves raw data and performs calculations at serving time, allowing flexible handling of logic changes without re-collecting data.

# 🛠️ Prerequisites
Requires a Python 3.8+ environment.

```Bash

pip install -r requirements.txt
```

# 🚀 How to Run
## 1. Configure GitHub Token (Optional)
* Using a token is recommended to avoid GitHub API rate limits (60 requests/hour). Set it as an environment variable or configure it before running app.py.

Linux/Mac:

```Bash
export GITHUB_TOKEN="your_github_token_here"
```

Windows (PowerShell):

```PowerShell
$env:GITHUB_TOKEN="your_github_token_here"
```
## 2. Run Server
```Bash
python app.py
```
* The browser opens **automatically upon** execution (http://127.0.0.1:5000).

* Data is fetched from GitHub on the first run and subsequently saved to `conferences_data.json`.

# Runtime Screen
<img src="./figures/example 1.png"></img>
<img src="./figures/example 2.png"></img>

# ⚠️ Note
* If no data appears on the screen, you may have reached the GitHub API Rate Limit. Please configure a token or try again in about an hour.

* Clicking the [Update] button in the top right corner forces a fetch of the latest data.