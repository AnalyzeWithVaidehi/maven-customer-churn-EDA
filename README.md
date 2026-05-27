# 📉 Maven Music Customer Churn Analysis: 🧹 Data Cleaning & EDA :

## 👋 Meet the Analyst
Hi, I'm Vaidehi! I am a Data Analyst specializing in bridging the gap between raw data chaos and clean, reliable business strategies. With a background in computer science and digital marketing analytics, I don't just look at data as numbers in a grid—I look at it as a map of customer behavior and operational health.

* **🛠 My Tech Stack:** Excel, Power BI/Tableau, SQL (Window Functions, CTEs, Complex Joins) and Python (Pandas, Numpy, Matplotlib, Seaborn).
* **🎯 My Philosophy:** A model or dashboard is only as good as the scoping behind it. Before writing a single line of SQL or Python, I focus heavily on product thinking, stakeholder alignment, and defining clear metric boundaries to ensure data projects solve real business problems.
* **📬 Connect with Me:** [linkedin](https://www.linkedin.com/in/vaidehibharambeaulagar)| vaidehibh@gmail.com

---

## 📌 Phase 1: Project Scoping & Architecture

### Why This Project?
Maven Music is a streaming service experiencing a worrying trend: they are losing more customers than usual, causing their monthly revenue growth to slow down significantly. If an analyst immediately jumps into writing code or building models without understanding this friction, they risk wasting weeks solving the wrong problem.

**My Mission:** Step in as the data analyst to systematically scope this data science project.I translated a broad business anxiety ("we are losing revenue") into a precise, structured supervised learning architecture with a clearly defined timeline and measurable objectives.

### The Scoping Framework: Core Decisions & Mapping
Indepth scoping of the project can be found here [📉 Maven Music Project Scoping: Translating Customer Churn into a Supervised Learning Strategy](https://github.com/AnalyzeWithVaidehi/maven-customer-churn-project-scoping)


## 📌 Project Overview
* **Objective:** Perform in-depth Exploratory Data Analysis (EDA) and transition raw data into a structured format for machine learning.
* **The Goal:** Predict customer subscription cancellations using three months of listening history and account data.
* **The Challenge:** Unified a multi-tab Excel file and a separate CSV file into a single cohesive dataset.

---

## 🛠️ Data Gathering & Cleaning
* **Data Sources:** Imported `maven_music_customers.csv` and multiple sheets from `maven_music_listening_history.xlsx` using Pandas.
* **Type Conversions:** Converted string dates to datetime objects and stripped dollar signs from subscription rates to convert them into floats.
* **Missing Data:** Imputed missing subscription plans with the "Basic (Ads)" tier based on price analysis.
* **Binary Encoding:** Converted discount flags into standard binary `1` and `0` values.
* **Standardization:** Corrected subscription price typos (e.g., $99.99 to $9.99) and unified inconsistent genre naming conventions (e.g., merging "Pop Music" into "Pop").
* **Feature Creation:** Engineered a binary `Canceled` target variable and cleaned email string prefixes for cleaner tracking.

---

## 📊 Exploratory Data Analysis (EDA)
* **The Discount Effect:** 85% of customers who received a discount canceled, compared to only 30% of those without a discount. Discount-seekers highly churn once promotions end.
* **Customer Lifespan:** Churned customers stayed for an average of only 46 days.
* **Listening Habits:** Merged audio and listening history tables by splitting and standardizing string-based IDs. Pop was identified as the most popular genre by a significant margin.

---

## ⚙️ Feature Engineering for Machine Learning
* **The Model DataFrame:** Aggregated data into a clean `model_df` where each row represents a single unique customer.
* **Session Volume:** Grouped data to calculate the unique number of listening sessions per customer over the three-month period.
* **Content Preferences:** Used One-Hot Encoding (`pd.get_dummies()`) to transform text genres into numerical data.
* **Consumption Metrics:** Calculated the percentage of total audio consumed for specific genres like Pop and Podcasts.

---

## 💡 Key Business Insights
* **Discount (Positive Correlation):** Promotions actively drive churn. Users are loyal to the price drop, not the platform.
* **Number of Sessions (Negative Correlation):** Frequent logins serve as one of the strongest predictors of customer retention.
* **Percent Pop (Strong Negative Correlation):** Pop music fans show a high affinity for the service and rarely cancel.
* **Percent Podcast (No Correlation):** Podcast consumption is currently "churn-neutral" and does not influence retention.

---

## 📂 What’s Inside This Repository?

* 📁 data/maven.db   : Raw data files
*  |---------/maven_music_cutomers.csv
*  |---------/maven_music_listening_history.xlsx
*  |---------/maven_music_cutomers.csv
*  📁 notebook/Maven_Music_EDA.ipynb : EDA Analysis notebook
* 📄 `README.md`: The strategic operational blueprint.
* 📄`My Thought Process.pdf`: File that contains what was I thinking during Data Cleaning and EDA process.
---

## ✅ Key Takeaways: Data Execution Strategy

This project showcases an end-to-end analytical workflow—moving from cold business scoping directly into programmatic execution.
* By maintaining a clean documentation footprint, checking data constraints early, and engineering targeted features, this process guarantees that subsequent machine learning steps are built on a verified, business-aligned foundation.
---
## 🎯The "So What?"
* I recommended the business to focus on engaging users through **Pop Music** content and **reconsider the discount strategy**, as it was attracting high churn customers rather than loyal subscribers.
---
## 🚀 What's Next? (Future Roadmap)

Now that the data is clean and structured, the next logical phase would translate these insights into automated business actions:

* **Predictive Modeling:** Train a machine learning model to assign a "churn risk score" to every active subscriber based on their usage patterns.
* **Catching Attrition Early:** Tune the model to prioritize catching high-risk users. In subscriber economics, missing a customer who is about to leave is far more costly than reaching out to a loyal one.
* **Automated Retention Actions:** Turn the model's scores into real-time triggers. For example, if a user's streaming activity drops below their personal average, automatically trigger a personalized re-engagement campaign or special offer to win them back.
