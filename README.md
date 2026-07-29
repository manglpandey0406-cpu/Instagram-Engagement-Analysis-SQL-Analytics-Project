# Instagram-Engagement-Analysis-SQL-Analytics-Project
Analyzed Instagram user data across 7 relational tables using SQL to uncover engagement patterns, retention gaps, and influencer opportunities. Used window functions, CTEs, and segmentation to identify power users and top hashtags, delivering a data-driven marketing action plan for Meta's team.
# Instagram Engagement Analysis — SQL Analytics Project

A SQL-driven analysis of Instagram user activity data, built to help Meta's Marketing team uncover engagement, retention, and influencer-marketing opportunities using pure SQL — no spreadsheet tools.

## 📌 Project Overview

Acting as a data analyst partnering with Meta's Marketing team, this project mines Instagram's core relational data (users, content, social graph, and reactions) to answer three business questions:

- **Engagement** — Which users, posts, and hashtags actually drive likes and comments?
- **Retention** — Who is fading into inactivity, and what would bring them back?
- **Acquisition** — Which power users and influencers can extend Instagram's reach the furthest?

All conclusions are backed by SQL queries run directly against the dataset — no guesswork.

## 🗂️ Repository Contents

| File | Description |
|---|---|
| `ig_clone_final.sql` | Full SQL script — data quality checks and all objective/subjective analysis queries |
| `sql_project_final.pptx` | Presentation summarizing the schema, analysis, insights, and recommendations |
| `sql_project.docx` | Written report documenting the analysis process and conclusions |

## 🧱 Database Schema

Seven linked tables covering identity, content, the social graph, and engagement:

| Table | Purpose |
|---|---|
| `users` | Platform identity |
| `photos` | Posted content |
| `follows` | Social graph (follower ↔ followee) |
| `likes` | Reactions to posts |
| `comments` | Reactions to posts |
| `tags` | Hashtag taxonomy |
| `photo_tags` | Link between posts and hashtags |

**Data quality:** `GROUP BY` / `HAVING COUNT(*) > 1` duplicate scans and NULL scans were run across all seven tables — **0 duplicates, 0 missing values** found.

## 🔍 Analysis Performed

The `.sql` script is organized into objective and subjective question sets, using:
- **Window functions** (`DENSE_RANK()`) for engagement leaderboards, including a monthly partitioned ranking
- **CTEs** to calculate average engagement per hashtag before ranking
- **CASE-based segmentation** to tier users into Highly Active / Moderately Active / Low Activity / Inactive
- **Joins across the social graph** to identify mutual-follow patterns and influencer candidates
- **Aggregate engagement metrics** (likes + comments per post, tags per post) to surface top performers

## 📊 Key Insights

- **A narrow top ~10% of users (power users)** generate a disproportionate share of engagement — e.g., the top-ranked user hit 75 engagements/post, with the top 10 clustering between 65–75.
- **Monthly leaderboards show the same concentration** period over period, not a one-time spike.
- **Lifestyle and food-related hashtags** (`#delicious`, `#beauty`, `#foodie`) consistently outperform, all within a tight 64–65 engagement band — engagement is broad-based, not driven by one viral tag.
- **Reach ≠ engagement quality**: users with identical follower counts (77) showed real spread in engagement rate, meaning influencer selection needs both metrics, not follower count alone.
- **Inactivity is an activation gap, not churn** — a meaningful segment has never posted, liked, or commented, meaning onboarding fixes matter more than win-back campaigns.

## 💡 Recommendations

- **Tier-based outreach:** match marketing intensity to each user's activity tier — recognition for Highly Active, nudges for Moderately Active, single-action prompts for Low Activity, and full onboarding flows for Inactive users.
- **Dual-metric influencer selection:** prioritize users who score high on both follower count *and* engagement rate for flagship partnerships; track high-rate/lower-follower users as micro-influencer candidates.
- **Content and ad targeting:** anchor campaigns around the top-performing hashtags identified in the analysis.
- **Recurring recognition program:** a monthly "Top 10 Engaged Users" leaderboard, refreshed via the same ranking query, to keep power users invested.
- **Validate before scaling:** treat top tags and influencer picks as A/B test hypotheses before committing full campaign budgets.

## 🛠️ Tools Used

- **SQL** — joins, CTEs, window functions, CASE-based segmentation, data quality auditing
- **PowerPoint** — insights and recommendation presentation
- **Word** — written analytical report

## 🎯 Skills Demonstrated

- Relational data modeling and schema design
- Advanced SQL querying (window functions, CTEs, ranking, segmentation)
- Data quality auditing (duplicate/null checks)
- Translating query outputs into a marketing action plan

## 👤 Author

**Abhishek**
Aspiring Data Analyst

---
*This project was completed as a personal SQL analytics submission based on a simulated Instagram user activity dataset.*
