<div align="center">

# 🎓 The Online Learning Landscape
### An interactive Power BI teardown of 8,000+ courses across Coursera, Udacity, Simplilearn & FutureLearn

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/status-complete-3ddc84?style=for-the-badge)
![Data](https://img.shields.io/badge/rows-8%2C092-6C63FF?style=for-the-badge)

*What are 8,000 online courses actually telling us about how the world learns to code, build, and think? This dashboard goes looking for the answer.*

</div>

---

## 🧭 The Question This Started With

Every course platform claims to have "something for everyone." I wanted to know if that was actually true, or if — underneath the marketing — every catalog quietly funnels learners toward the same handful of topics, the same handful of languages, and the same handful of "star" instructors.

So I pulled a raw export of courses, specializations, and professional certificates from four major platforms and built a Power BI report to interrogate it.

<!-- 📸 Add your dashboard overview screenshot here -->
![Dashboard Overview](assets/01-overview.png)

---

## 🔍 What the Data Actually Says

| Finding | The Number | Why It's Interesting |
|---|---|---|
| **English dominates almost totally** | `97.36%` of all listed courses | Only `2.62%` sit in Spanish, and every other language — French, Japanese, Chinese, Portuguese, Russian — splits a sliver under `2%` combined |
| **"Courses" crush every other format** | Standalone courses outnumber Specializations & Professional Certificates by **~30–40x** | Platforms are optimizing for volume and quick wins, not deep multi-course tracks |
| **Data Science is the attention magnet** | `6,383` avg. views/category — highest of any category | Beats Information Technology (`4,648`), Computer Science (`4,404`), Personal Development (`3,221`), and Language Learning (`2,925`) |
| **Longer isn't always better — until it suddenly is** | Viewership stays flat (`0K`–`5K`) until ~500-700 hrs of content, then **spikes to `26.3K`** | A handful of marathon, high-duration programs pull in disproportionate viewership — the "go big or go unnoticed" effect |
| **Skill vocabulary is Python-and-SQL-shaped** | `Python Programming`, `Data Analysis`, `Machine Learning`, `SQL`, `Data Visualization` dominate the skills word cloud | Confirms the market has converged hard on a data/AI skill stack, regardless of category |
| **Data Science courses pack the most skills per course** | `4.74` avg. skills/course — highest across all categories | vs. `3.02` for Health and `3.79` for Business — Data Science courses are simply denser |

<!-- 📸 Add your "Most Prominent Language" pie chart screenshot here -->
![Language Breakdown](assets/02-language.png)

---

## 🖥️ Inside the Report

The `.pbix` is built as a **3-page interactive drilldown**, not a static snapshot — every visual is cross-filtered by the Category and Sub-Category slicers at the top.

### Page 1 — The Big Picture
- **Course Type Popularity** — a horizontal bar comparing Course vs. Specialization vs. Professional Certificate volume
- **Courses per Language & Sub-Category** — a dense clustered view of viewership by language, sliceable down to sub-category
- **Most Prominent Language** — donut breakdown of the English/Spanish/French/Japanese/Chinese/Portuguese/Russian split

<!-- 📸 Add your Page 1 screenshot here -->
![Page 1](assets/03-page1.png)

### Page 2 — Skills & Category Deep Dive
- **Skills Word Cloud** — every skill tag in the dataset, sized by frequency (Python, SQL, and Machine Learning visually dominate)
- **RANK_CATEGORY_BY_AVG_VIEWS** — a DAX-ranked table surfacing which categories actually hold attention, not just headcount
- **Average Skills vs. Course Count by Category** — a matrix pairing course *density* against course *volume*
- **Viewers by Subtitle Count** — an S-curve showing viewership exploding once subtitle/language accessibility crosses a threshold

<!-- 📸 Add your Page 2 screenshot here -->
![Page 2](assets/04-page2.png)

### Page 3 — Instructors & Duration
- **Instructor Rating by Instructor** — sub-category filtered leaderboard of top-rated instructors
- **Viewership vs. Duration** — a scatter/line tracing how course length correlates (or doesn't) with audience size

<!-- 📸 Add your Page 3 screenshot here -->
![Page 3](assets/05-page3.png)

---

## 🗂️ Repo Structure

```
online-courses-dashboard/
├── Online_Courses.csv         # Raw source data (8,092 courses, 43 columns)
├── powerbidashboard.pbix      # The full interactive Power BI report
├── assets/                    # Dashboard screenshots (referenced above)
└── README.md
```

---

## 🧱 About the Data

- **Rows:** 8,092 individual courses / specializations / certificates
- **Sources:** Coursera, Udacity, Simplilearn, FutureLearn
- **Categories:** Data Science, Computer Science, Business, Information Technology, Health, Language Learning, Math and Logic, Personal Development, Physical Science and Engineering, Social Sciences, Arts and Humanities
- **Key fields:** Title, Category/Sub-Category, Course Type, Language & Subtitle Languages, Skills, Instructors, Rating, Number of Viewers, Duration, Level, Price

The raw export includes messy, platform-specific columns (multiple access-length pricing tiers, CRM topics, ExpertTracks, FAQs, etc.) — part of the build was cleaning and reshaping this into fields the model could actually rank, filter, and slice on.

---

## ⚙️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures (`RANK_CATEGORY_BY_AVG_VIEWS`, avg-views-by-category), and report design
- **Power Query** — cleaning multilingual category labels, parsing duration strings, unpivoting skill tags

---

## 🚀 Run It Yourself

1. Clone the repo
2. Open `powerbidashboard.pbix` in **Power BI Desktop**
3. If the data source path breaks, repoint it at `Online_Courses.csv` in **Home → Transform Data → Data Source Settings**
4. Use the Category / Sub-Category slicers at the top of each page to explore

---

<div align="center">

*Built to answer one question — turned into a full teardown of how the online learning market actually behaves.*

</div>
