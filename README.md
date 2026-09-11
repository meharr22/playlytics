#  Playlytics
### Turning Player Data into Winning Strategies

![Power BI](https://img.shields.io/badge/PowerBI-Analytics-yellow?logo=powerbi)
![DAX](https://img.shields.io/badge/DAX-Data_Modeling-blue)
![Power Query](https://img.shields.io/badge/Power_Query-ETL-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

##  Project Overview

Playlytics is an end-to-end Gaming Analytics Dashboard built in Power BI to uncover insights into player behavior, engagement patterns, monetization performance, and churn risk.

The goal was to transform raw gaming data into actionable business intelligence that helps stakeholders understand:

- Who their players are
- How players engage with games
- What drives revenue
- Which users are at risk of churn
- How acquisition channels perform

This dashboard simulates a real-world gaming company's analytics environment and demonstrates practical Business Intelligence, Data Modeling, and Data Visualization skills.

---

#  Business Problem

Gaming companies generate massive amounts of user activity data every day.

Without proper analytics, it becomes difficult to answer questions such as:

- Which game modes are most popular?
- How engaged are players?
- Which users generate the most revenue?
- What factors contribute to churn?
- Which marketing channels bring valuable users?

Playlytics was built to answer these questions through interactive dashboards and KPI-driven reporting.

---

#  Tech Stack

### Analytics & Visualization
- Power BI Desktop
- DAX
- Power Query

### Data Processing
- Data Cleaning
- Data Transformation
- Feature Engineering

### Data Modeling
- Star Schema Design
- Date Table Creation
- Relationships Management

### KPIs Created
- DAU (Daily Active Users)
- MAU (Monthly Active Users)
- ARPU (Average Revenue Per User)
- Total Revenue
- Total Hours Played
- Average Achievement Score
- User Retention Metrics

---

#  Dashboard Pages

##  User Overview

Provides a high-level snapshot of platform performance.

### Key Metrics
- Total Users
- Total Revenue
- Gender Distribution
- Geographic User Distribution
- User Growth Trend

### Key Insight
The platform maintains a diverse player base with balanced demographic participation and stable growth trends.

---

##  Engagement Patterns

Analyzes how users interact with games.

### Key Metrics
- Average Achievement Score
- User Activity Status
- Preferred Game Mode
- Rank Tier Analysis

### Key Insight
Co-op gameplay emerges as the most preferred mode, indicating strong demand for collaborative gaming experiences.

---

##  Monetization Performance

Tracks revenue-related KPIs and player spending behavior.

### Key Metrics
- Monthly Revenue Trend
- Top Revenue-Generating Users
- Revenue by Device Type
- Average Revenue Per User (ARPU)

### Key Insight
Revenue remains consistently strong throughout the year while PC and Console users contribute almost equally.

---

##  Churn & Retention Risk

Identifies retention opportunities and user engagement risks.

### Key Metrics
- Total Hours Played
- Referral Source Performance
- Session Count Distribution
- Active vs Inactive Users

### Key Insight
A significant portion of users remain inactive, creating opportunities for targeted re-engagement campaigns.

---

#  Key Business Insights

###  User Base
- 6,662 Total Users
- Balanced gender distribution
- Globally diversified player base

###  Engagement
- 60%+ users remain active
- Co-op is the most preferred game mode
- Strong achievement participation

###  Revenue
- Total Revenue: 335K+
- ARPU: 50.22
- Stable revenue trend across months

###  Retention
- 671K+ gameplay hours
- Majority of users fall within medium-to-high engagement segments
- Inactive users present a major growth opportunity

---

#  Data Preparation Workflow

### Power Query Transformations

 Promoted Headers

 Data Type Conversion

 Signup Month Creation

 Days Since Last Login Calculation

 Active/Inactive User Classification

 Duplicate Removal

 Data Validation

---

#  Data Modeling

A dedicated Date Table was created using:

```DAX
DateTable = CALENDARAUTO()
```

Relationships were established to support:

- Time Intelligence
- DAU Analysis
- MAU Analysis
- Trend Reporting

---

#  Sample DAX Measures

### Daily Active Users

```DAX
DAU =
CALCULATE(
    DISTINCTCOUNT(Sheet1[User_ID]),
    USERELATIONSHIP(DateTable[Date], Sheet1[Last_Login])
)
```

### Monthly Active Users

```DAX
MAU =
CALCULATE(
    DISTINCTCOUNT(Sheet1[User_ID]),
    DATESINPERIOD(
        DateTable[Date],
        MAX(DateTable[Date]),
        -31,
        DAY
    )
)
```

### Average Revenue Per User

```DAX
ARPU =
DIVIDE(
    SUM(Sheet1[Total_Revenue_USD]),
    DISTINCTCOUNT(Sheet1[User_ID])
)
```

---



#  What I Learned

Through this project, I strengthened my understanding of:

- Power BI Dashboard Development
- DAX Calculations
- Time Intelligence Functions
- Power Query Transformations
- Data Modeling Best Practices
- KPI Design
- Storytelling with Data

---

#  Future Enhancements

- Cohort Analysis
- Churn Prediction Model
- Player Segmentation
- Revenue Forecasting
- Real-Time Dashboard Integration

---

## Author

**Mehar Arora**
