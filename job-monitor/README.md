# 🎯 Raaga's Job Monitor

A personal job monitoring dashboard that automatically fetches and filters relevant job postings every 2 hours.

**→ [View Live Dashboard](https://YOUR_USERNAME.github.io/job-monitor)**

## What it tracks

- **Roles**: Data Scientist, ML Engineer, Data Analyst, AI Engineer, Analytics Engineer
- **Level**: Mid-level (2–5 years)
- **Location**: All locations (remote + onsite)

## Sources

| Source | Type |
|--------|------|
| RemoteOK | Remote jobs API |
| Arbeitnow | Global tech jobs API |
| The Muse | Mid-level roles API |
| Himalayas | Remote jobs API |
| Greenhouse | Direct company boards |
| Lever | Direct company postings |
| Indeed | RSS feed |
| Jobright.ai | AI-matched listings |

## Setup (5 minutes)

### 1. Fork / Clone this repo

```bash
git clone https://github.com/YOUR_USERNAME/job-monitor
cd job-monitor
```

### 2. Enable GitHub Pages

- Go to **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: `main`, folder: `/ (root)`
- Click **Save**

### 3. Run the first fetch

- Go to **Actions → Job Monitor — Refresh Every 2 Hours**
- Click **Run workflow**
- Wait ~2 minutes for it to complete
- Visit your GitHub Pages URL!

### 4. (Optional) Run locally

```bash
pip install requests pandas openpyxl beautifulsoup4 lxml
python scripts/fetch_jobs.py
open index.html
```

## Files

```
job-monitor/
├── .github/workflows/job-monitor.yml   # Runs every 2 hours
├── scripts/fetch_jobs.py               # Job fetching + HTML + Excel generation
├── index.html                          # Live dashboard (auto-updated)
├── jobs.json                           # Raw job data (auto-updated)
└── job_monitor.xlsx                    # Downloadable spreadsheet (auto-updated)
```

## Customizing

Edit `scripts/fetch_jobs.py` to:

- **Add companies**: Add slugs to `GREENHOUSE_COMPANIES` or `LEVER_COMPANIES`
- **Change titles**: Edit `TARGET_TITLES` list
- **Filter level**: Adjust `EXCLUDE_TITLES` list
- **Change frequency**: Edit the cron in `.github/workflows/job-monitor.yml`

---
*Auto-refreshes every 2 hours via GitHub Actions*
