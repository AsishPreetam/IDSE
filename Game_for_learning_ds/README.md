# DataQuest – Data Cleaning Simulator

An educational Streamlit game where players clean generated employee, customer, and student datasets through five progressively unlocked missions.

## Run locally

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
streamlit run app.py
```

Open the local URL printed by Streamlit. In VS Code, open this folder, use **Terminal → New Terminal**, run the commands above, and keep the terminal running while playing.

## Gameplay and calculations

- Missing values use Pandas `isna`, `fillna`, mean, median, mode, and `dropna`.
- Duplicate detection and removal use `duplicated` and `drop_duplicates`.
- Formatting uses Pandas string operations and tolerant `to_datetime` parsing.
- Outlier flags use Q1/Q3 quantiles and the 1.5×IQR fences; values can be retained, capped, or removed.
- Session State holds the original and working DataFrames, level unlocks, XP, operation history, and feedback. Data regenerates on a fresh session.
- Plotly displays live distributions. The final challenge scores missingness, duplicates, formatting, outlier handling, and record retention.

## Playtesting with classmates

Ask a classmate to play each mission without coaching. Use the feedback template on the home page to note where the controls were unclear, whether feedback explained consequences, what concept they learned, and one suggested improvement. Do not enter personal or sensitive data.

Click **Save feedback** after entering a response. Entries are stored in this browser's local storage, so they remain after closing and reopening the browser on the same device and browser profile. They are not shared across devices or browser profiles and are removed if that browser's site data is cleared. Use **Download saved feedback** for a separate backup. This avoids relying on Render's ephemeral filesystem or an expiring free database.

## Render

`render.yaml` defines the Python web service, build command, and Streamlit start command using Render's `$PORT`. Connect the repository in Render and confirm the requested service name is available before deploying. Streamlit listens on `0.0.0.0` and runs headless.
