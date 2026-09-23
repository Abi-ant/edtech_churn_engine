# EdTech Student Engagement, Course Completion & Subscription Churn Engine



## 📌 Executive Summary
This project diagnoses student drop-off drivers and subscription churn mechanics for an online learning platform using **10M+ daily VLE clickstream interaction logs** (~32,500 students across 22 course modules). Leveraging **DuckDB, Python (Pandas/SciPy), and Tableau Public**, this engine models 12-week cohort engagement decay, identifies early-activity churn risk thresholds, and isolates high-friction assessment bottlenecks.

## Technical Architecture & Workflow
1. **DuckDB (SQL Data Staging):** Ingested raw clickstream telemetry, handled negative pre-course date offsets, standardized assessment weights, and built staged analytical views (`stg_student_registrations`, `stg_vle_interactions`).
2. **Python (Cohort Decay & Statistical Testing):** Built a 12-week active retention matrix and ran Welch's t-tests to isolate Week 2 activity thresholds predicting eventual churn.
3. **Tableau Public:** Assembled an interactive 2-page executive report complete with click-to-filter action triggers.

---

## Key Insights & Business Impact
- **Early Withdrawal Concentration:** 68% of course withdrawals occur within the first 14 days.
- **$2\times$ Churn Risk Marker:** Low-activity Week-2 learners (<15 mins study time) exhibit a **30.5% churn rate**, compared to **16.0%** for optimal learners (180+ mins).
- **Assessment Bottlenecks:** Foundational module quizzes suffered pass-rate drops down to 52%, driving subsequent platform inactivity.

---

## Strategic Recommendations
1. **Day-5 Triggered Study Nudges:** Automate study prompts when Week 1–2 active time falls below 45 minutes.
2. **Micro-Lesson Restructuring:** Break high-friction module assignments into smaller, progressive learning blocks.
