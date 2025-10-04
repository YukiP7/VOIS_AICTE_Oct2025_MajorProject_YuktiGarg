# 🎬 Netflix Content Trends Analysis for Strategic Recommendations  

## 🌟 Project Overview  
This project provides a comprehensive analysis of **Netflix's content catalog**, including Movies and TV Shows, spanning from **2008 to 2021**.  
The goal is to identify **shifting content trends**, **audience preferences (by genre and country)**, and derive **strategic recommendations** for future content acquisition and production to maintain a competitive edge against rival streaming platforms.  

---

## 🎯 Problem Statement  
Netflix must strategically analyze its vast content catalog to identify **strengths, gaps, and opportunities** amidst growing competition (Amazon Prime, Disney+, etc.).  

The core problem addressed is:  
**"Content Trends Analysis for Strategic Recommendations"**  

Focus Areas:  
- How content distribution (**Movies vs. TV Shows**, **genres**, and **country contributions**) has evolved over the years.  
- Providing insights to inform **global content expansion strategies**.  

---

## 🔑 Objectives  
- **Analyze Content Distribution** → Year-over-year balance and trend between Movies and TV Shows.  
- **Genre Analysis** → Identify the most common genres and evaluate how their popularity trended over time.  
- **Global Contribution** → Compare country-wise contributions to Netflix’s content library.  
- **Talent Identification** → Most frequent directors and cast members.  
- **Duration Analysis** → Distribution of Movie durations and TV Show seasons.  

---

## 📚 Libraries Used  

| Library           | Purpose |
|-------------------|---------|
| **pandas**        | Data manipulation and cleaning |
| **numpy**         | Numerical operations and arrays |
| **matplotlib.pyplot** | Static visualization |
| **seaborn**       | Statistical visualization (bar & line plots) |
| **plotly.express** | Interactive and geographic visualization (Choropleth Map) |

---

## ⚙️ Data Cleaning & Preprocessing  
- **Duplicate Handling** → 2 duplicate rows identified and removed.  
- **Missing Values** →  
  - *Director, Cast, Country* → filled with `"Unknown"`.  
  - *Rating* → filled with mode.  
  - *Release_Date* → 10 rows missing, dropped.  
- **Feature Engineering** →  
  - Converted *Release_Date* → datetime → extracted **Release_Year**.  
  - Split *Duration* → **Duration_min** (Movies) and **Seasons** (TV Shows).  
  - Standardized *Country* and *Type* columns → only primary entry (first listed).  

---

## 📊 Analysis and Visualizations  

### 1️⃣ Distribution of Movies and TV Shows Over the Years  
- Bar chart shows growth of Netflix content.  
- Notable **shift toward Movies** in recent years.  

📈 *Chart Example:*  
 <img width="1200" height="600" alt="distribution_movies_tv_over_years" src="https://github.com/user-attachments/assets/2d0bdc7d-c119-404d-8032-6751e0cf3137" />

---

### 2️⃣ Top 5 Most Common Genres  
- **Top Genres:**  
  1. Dramas (1384 titles)  
  2. Comedies (1074 titles)  
  3. Documentaries (751 titles)  
  4. Action & Adventure (721 titles)  
  5. International TV Shows (689 titles)  

- **Trend Analysis** → Line plot shows how top 5 genres peaked over years.  

📊 *Chart Example:*  
<img width="1200" height="400" alt="most_common_genres_filtered" src="https://github.com/user-attachments/assets/f43f905a-7ff4-4309-a5f6-e0c4bfc078f8" />

<img width="1200" height="600" alt="genre_trend_over_years" src="https://github.com/user-attachments/assets/0f6d7cd4-4b4b-4d89-8de0-c0c9a86490e2" />

---

### 3️⃣ Content Distribution by Country  
- **Plotly Choropleth Map** highlights **global contributions**.  
- Largest contributors: **United States, India, United Kingdom, South Korea**.  

🌍 *Interactive Map Code:*  

```python
fig = px.choropleth(
    country_counts,
    locations="Country",
    locationmode="country names",
    color="Count",
    hover_name="Country",
    title="Netflix Content Distribution by Country",
    color_continuous_scale="Reds"
)
fig.show()
```


<img width="1245" height="525" alt="newplot" src="https://github.com/user-attachments/assets/d6f0461c-982d-4492-872b-28466dc94184" />

----

### Most Frequent Director & Cast 
| Category          | Most Frequent |
|-------------------|---------|
| **Director**      | Jan Suter |
| **Cast**          | Anupam Kher |


## 📌 Content Duration Analysis  

- **Movies** → Average runtime ≈ **99.3 mins**  
- **TV Shows** → Most are **1-season series (1608 titles)**, followed by **2 seasons (378 titles)**  

📊 **Charts:**  
- Histogram → Movie Duration Distribution  
- Bar Chart → TV Show Season Counts

<img width="1000" height="500" alt="movie_duration_distribution" src="https://github.com/user-attachments/assets/5fd51dea-4b3b-4dbd-a834-6e4d17660c0d" />
<img width="1000" height="500" alt="tv_show_seasons_distribution" src="https://github.com/user-attachments/assets/213b0a7d-cdb1-4902-ac69-3e0ae43adde7" />

------
## ✨ Summary of Key Insights  

1. **Movie-Heavy Strategy**  
   - Surge in **Movies after 2019**.  

2. **Dominant Genres**  
   - **Dramas & Comedies** drive the catalog.  

3. **Genre Peaks**  
   - Most genres **peaked around 2019**, possibly due to a large content acquisition push.  

4. **Key Markets**  
   - **US & India** dominate contributions → showing focus on **English + Indian content**.  

5. **Short-Form TV**  
   - Majority are **single-season shows** → aligns with the **limited series trend**.  

6. **Talent Network**  
   - Frequent collaborations with **Indian actors (e.g., Anupam Kher)** & **comedy-special directors (Jan Suter, Raúl Campos)**.  

