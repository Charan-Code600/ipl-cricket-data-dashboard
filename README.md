




# 🏏 IPL/Cricket Data Dashboard

A menu-driven command-line application built with **Python** and **Pandas** that analyzes IPL match data — team performance, head-to-head records, top players, venue trends, and season champions — all visualized through an interactive terminal dashboard.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge&logo=plotly&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

---

## 🚀 Overview

IPL/Cricket Data Dashboard is a lightweight, terminal-based analytics tool for exploring IPL match history. It turns a raw CSV of match records into instant insights — who wins the most, how two teams stack up against each other, which players show up in the big moments, and which venues host the most cricket.

Unlike the earlier projects in this series, this is a **read-only analytics dashboard** — it doesn't collect new data, it analyzes an existing dataset, making it a strong showcase of `groupby`, `value_counts`, and multi-condition filtering in Pandas.

---

## ✨ Features

| # | Feature | Description |
|---|---------|-------------|
| 1 | 👀 **View All Matches** | Displays the complete match dataset |
| 2 | 🏆 **Team-wise Wins** | Ranks every team by total match wins |
| 3 | ⚔️ **Head-to-Head Record** | Compares any two teams' historical record against each other |
| 4 | ⭐ **Top Player of the Match** | Shows the top 5 most frequent Player-of-the-Match winners |
| 5 | 🏟️ **Venue-wise Match Count** | Shows how many matches were played at each venue |
| 6 | 👑 **Season-wise Champion** | Lists the winning team for each IPL season |
| 7 | 📊 **Visualize Data** | Bar chart of team-wise wins across the dataset |

---

## 🛠️ Tech Stack

- **Python 3** — core logic
- **Pandas** — data aggregation, filtering & analysis (`groupby`, `value_counts`, multi-condition filtering)
- **Matplotlib** — data visualization

---

## 🧠 What Makes This Robust

- ✅ **Auto-recovery** — missing or empty `ipl_matches.csv` is detected and handled gracefully instead of crashing
- ✅ **Case-insensitive team lookup** — Head-to-Head search works regardless of how team names are typed (`csk`, `CSK`, `Csk` all match)
- ✅ **Graceful unknown-team handling** — searching for teams with no shared match history returns a clear message instead of an error
- ✅ **Empty-data handling** — every feature checks for missing data first and responds with a clear message
- ✅ **Full exception handling** — every menu action is wrapped so unexpected errors never crash the session

---

## 💻 Sample Run

```
************************************************
╔══════════════════════════════════════════════╗
║         IPL/CRICKET DATA DASHBOARD           ║
╚══════════════════════════════════════════════╝
************************************************

    View All Matches             enter ---> 1
    Team-wise Wins               enter ---> 2
    Head-to-Head Record          enter ---> 3
    Top Player of the Match      enter ---> 4
    Venue-wise Match Count       enter ---> 5
    Season-wise Champion         enter ---> 6
    Visualize Data (Chart)       enter ---> 7
    Exit                         enter ---> 8

************************************************

Enter your choice: 3
Enter Team 1: csk
Enter Team 2: kkr

Head-to-Head: CSK vs KKR
Total Matches: 4
CSK Wins: 1
KKR Wins: 3
```

---

## ⚙️ Getting Started

**1. Install dependencies:**
```bash
pip install pandas matplotlib
```

**2. Run the program:**
```bash
python ipl_cricket_dashboard.py
```

Make sure `ipl_matches.csv` is present in the same folder, with the following columns:
`Season, Team1, Team2, Winner, Venue, PlayerOfMatch`

---

## 📁 Project Structure

```
📦 ipl-cricket-data-dashboard
 ┣ 📜 ipl_cricket_dashboard.py   # Main application
 ┣ 📜 ipl_matches.csv            # IPL match dataset
 ┗ 📜 README.md                  # You are here
```

---

## 🧪 Testing

This project was manually tested end-to-end, covering:
- Data loading and column integrity
- Team-wise win counts verified against raw match data
- Head-to-head record accuracy (including case-insensitive input)
- Unknown-team lookups
- Top player rankings
- Venue-wise match distribution
- Season-wise champion accuracy
- Chart rendering across all teams
- Invalid menu choices

---

## 👤 Author

**Charan Aade | Python & Data Analysis Developer**

🔗 [GitHub](https://github.com/Charan-Code600)
