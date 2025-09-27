# 🎮 Analysis of New and Returning A Game Users Trends

**Analysis Date:** April 30, 2022

---

## 1️⃣ Overview

### Background

Following the release of the highest-level expansion (95 → 100), the "True Ascension" update, and the launch of Mythical items on January 9, 2020:

* PC café market share increased by 30%
* Returning users increased more than fourfold
* New user acquisition also significantly increased

> This analysis was conducted to understand the behavior and trends of new and returning users after these updates.

### Methodology and Analysis Period

* **Methodology:** In-house analysis using Python & Excel
* **Analyst:** Juwon Park
* **Analysis Period:** April 23, 2022 – April 30, 2022

### Analysis Approach

* **Data Sources:** Crawled posts from free bulletin boards of Akararive, A Game Inven, and A Game Naver Cafe
* **Text Mining Techniques:**

  * Frequency Analysis
  * Network Analysis
  * Sentiment Analysis

---

## 2️⃣ Dataset

### Sources

| Site                     | Features                                           | Included in Analysis |
| ------------------------ | -------------------------------------------------- | -------------------- |
| A Game OFF               | Character stats, buffs, skill trees of top players | ❌ Excluded           |
| Akararive A Game Channel | Community posts related to A Game                  | ✅ Included           |
| A Game Inven             | Latest information, tips, guides, community        | ✅ Included           |
| A Game Naver Cafe        | Naver Cafe related to A Game                       | ✅ Included           |

> **Note:** A Game OFF excluded due to excessive simple inquiries unsuitable for trend analysis.

### Dataset Structure

```
Title | Author | Date Posted | Views | Recommendations | URL | Content
```

* Crawling Tools: Beautiful Soup & Selenium

### Utilized Data

| Data Name           | Description                          | Count |
| ------------------- | ------------------------------------ | ----- |
| Akararive_Returning | Posts containing keyword "returning" | 5,640 |
| Akararive_New       | Posts containing keyword "newbie"    | 9,989 |
| Inven               | Posts from A Game Inven              | 5,551 |
| NaverCafe_Returning | Posts containing keyword "returning" | 5,000 |
| NaverCafe_New       | Posts containing keyword "newbie"    | 5,000 |

---

## 3️⃣ Analysis Details

### 3.1 Keyword Analysis

#### Frequency Analysis

* Morphological Analysis: **Konlpy Okt**
* Visualization: **Word Cloud & Treemap** (Top 50 words)

#### Network Analysis

* Data: Post titles and content
* Centrality Measure: **Page Rank**
* Visualization Criteria: Item sets ≥ 2, Support ≥ 0.01

**Key Findings – New Users**

* Central word: **Epic**
* Strongly connected words: Equipment, Enhancement, Weapon, Dungeon
* Word Groups:

  * Items: Weapon, Equipment
  * Ranks: Mythic, Epic
  * Content: Raid, Dungeon, Farming, Event, Purgatory

**Key Findings – Returning Users**

* Central word: **Epic**
* Strongly connected word: Raid
* Word Groups:

  * Items: Weapon, Equipment
  * Ranks: Mythic, Epic
  * Dungeons: Raid, Dungeon, Farming

**New vs Returning Users Comparison**

* Shared top interest: **Mythic rank**
* Post type differences:

  * New users: predominantly questions
  * Returning users: mix of experiences and questions

---

### 3.2 Sentiment Analysis

#### Lexicon

* **Knu Lexicon** (Open-source, 14,855 words) selected for sentiment analysis

#### Site-specific Negative Keywords

| User Type | Akararive                | Inven                        | Naver Cafe                 |
| --------- | ------------------------ | ---------------------------- | -------------------------- |
| New       | Skill, Mythic, Equipment | Class, Recommendation, Start | Mythic, Raid, Modification |
| Returning | Mythic, Skill, Weapon    | Weapon, Farming, Dungeon     | Mythic, Raid, Crafting     |

> Negative sentiment dominated across all sites.

#### Monthly Trend Analysis (2021)

* Peak posting months: December & January

  1. Winter vacation events
  2. COVID-19 restrictions
  3. A Game Festival (Dec 20)
* Increased posts focused on Mythic, Epic, Weapons, Equipment
* Negative feedback often related to lack of updates (Raids, new characters)

---

## 4️⃣ Limitations

* Page limits: Naver Cafe (100), Akararive (333) → recent posts biased
* Knu lexicon does not include slang or neologisms
* Community posts biased toward negative experiences → internal game logs needed for complete behavioral insights

---

## 5️⃣ Recommendations

### Reflecting User Feedback

* Frequency analysis highlights user reactions
* Continuous updates for **Epic** items and increased dungeon difficulty recommended

### Advanced Analysis

* Internal data can cluster new and returning users for predictive analysis and efficient user management

---

## 6️⃣ Additional Analysis Topics

### Impact of PK on Attrition Rate

* PK (Player Killing) may negatively affect user retention
* Comparative analysis to determine PK’s effect
* Reducing attrition may lead to higher profitability

### Impact of Party/Guild Participation on Attrition

* Users participating ≥2 times/week in parties/guilds analyzed via network analysis
* Hypothesis: More active participation → higher retention
* Positive findings can guide strategies to encourage participation and build loyal user base
