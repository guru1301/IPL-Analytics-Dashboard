# 🏏 IPL Analytics Dashboard — Power BI

An interactive multi-season analytics dashboard covering **18 seasons (2008–2025)** of Indian Premier League data — built with Power BI using ball-by-ball, match, player, and team datasets.

---

## 📌 Overview

This dashboard delivers deep insights into IPL match performance, player statistics, team trends, and season-wise comparisons. Designed for cricket analysts, fans, and data enthusiasts looking to explore IPL data visually.

---

## 📊 Dashboard Features

- **Season Overview** — Match results, winners, and stage-wise breakdown per season
- **Team Performance** — Win/loss records, toss impact, venue analysis
- **Player Statistics** — Top run-scorers, wicket-takers, strike rates, economy rates
- **Ball-by-Ball Analysis** — Over-wise run flow, powerplay vs death overs
- **Player of the Match Trends** — Most impactful players across seasons
- **Head-to-Head Comparisons** — Team vs team historical records
- **Dynamic Filtering** — Filter by season, team, venue, and player

---

## 🗂️ Dataset

| File | Description | Records |
|------|-------------|---------|
| `ipl_matches_data.csv` | Match-level data (result, toss, venue, teams) | 1,169 matches |
| `ball_by_ball_data.csv` | Delivery-level data (runs, wickets, extras) | 2,78,205 balls |
| `players-data-updated.csv` | Player profiles (bat/bowl style, position) | 772 players |
| `teams_data.csv` | Team names and identifiers | 16 teams |

**Seasons covered:** 2008 – 2025

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| Power BI Desktop | Dashboard development |
| Power Query | Data cleaning & transformation |
| DAX | KPI measures & calculated columns |
| CSV | Raw data sources |

---

## 💡 Key DAX Measures Used

```dax
Total Runs = SUM('ball_by_ball_data'[batter_runs])

Strike Rate = 
DIVIDE(SUM('ball_by_ball_data'[batter_runs]), COUNTROWS('ball_by_ball_data')) * 100

Economy Rate = 
DIVIDE(SUM('ball_by_ball_data'[total_runs]), COUNTROWS('ball_by_ball_data')) * 6

Win % = 
DIVIDE(
    CALCULATE(COUNTROWS('ipl_matches_data'), 'ipl_matches_data'[match_winner] = SELECTEDVALUE('teams_data'[team_name])),
    COUNTROWS('ipl_matches_data')
) * 100
```

---

## 📁 Repository Structure

```
IPL-Analytics-Dashboard/
├── IPL_ANALYSIS.pbix              ← Power BI Dashboard file
├── ipl_matches_data.csv           ← Match-level dataset
├── ball_by_ball_data.csv          ← Ball-by-ball dataset
├── players-data-updated.csv       ← Player profiles
├── teams_data.csv                 ← Team data
└── README.md                      ← Project documentation
```

---

## 🚀 How to Open

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Clone or download this repository
3. Open `IPL_ANALYSIS.pbix` in Power BI Desktop
4. Refresh data if prompted

---

## 📈 Key Insights

- **18 seasons** of IPL data from 2008 to 2025
- **1,169 matches** and **2,78,205 deliveries** analysed
- Toss decision impact on match outcomes visualised
- Powerplay vs death over run rates compared across teams

---

## 👤 Author

**Guru Prasath M**  
Data & Backend Developer  
📧 mguruprasath01@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/guru-prasath-m130105) | [GitHub](https://github.com/guru1301)
