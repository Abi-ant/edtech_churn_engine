# EdTech Student Engagement, Course Completion & Subscription Churn Engine

## Executive Summary
This project diagnoses student drop-off drivers and subscription churn mechanics for an online learning platform using **10M+ daily VLE clickstream interaction logs** (~32,500 students across 22 course modules). Leveraging **DuckDB, Python (Pandas/SciPy), and Tableau Public**, this engine models 12-week cohort engagement decay, identifies early-activity churn risk thresholds, and isolates high-friction assessment bottlenecks.
---

## Technical Architecture & Workflow
1. **DuckDB (SQL Data Staging):** Ingested raw clickstream telemetry, handled negative pre-course date offsets, standardized assessment weights, and constructed staged analytical views (`stg_student_registrations`, `stg_vle_interactions`, `stg_assessment_results`).
2. **Python (Cohort Decay & Statistical Testing):** Modeled a 12-week active retention matrix and executed Welch's two-sample t-tests to validate Week 2 activity thresholds that predict eventual subscription churn.
3. **Tableau Public:** Assembled an executive-ready 2-page operational dashboard complete with dynamic click-to-filter action triggers and assessment friction detail views.

---

## Key Insights & Business Impact
- **Early Withdrawal Concentration:** 68% of all course withdrawals occur within the initial 14 days of enrollment.
- **$2\times$ Churn Risk Marker:** Low-activity Week 2 learners (<15 minutes study time) demonstrate a **30.5% churn rate**, compared to **16.0%** for optimal learners (180+ minutes)—a **1.91x elevated churn probability**.
- **Curriculum Assessment Bottlenecks:** Foundational module assignments (e.g., in modules BBB and DDD) exhibit failure rates reaching up to 48%, serving as the primary catalyst for log-off and eventual subscription cancellation.

---

## Recommended Strategic Actions
1. **Triggered Day-5 Study Nudges:** Automate study prompts and tutor outreach on Day 5 when a learner's Week 1–2 active time falls below 45 minutes.
2. **Micro-Lesson Restructuring:** Break high-friction module assignments into smaller, progressive learning blocks to flatten the difficulty curve and reduce drop-off.