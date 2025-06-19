<h1 align="center">🍽️ Zomato Restaurant Data Analysis</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Project-Data%20Analysis-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter" />
  <img src="https://img.shields.io/badge/Visualization-Seaborn%20%7C%20Matplotlib-yellow?style=for-the-badge" />
</p>

---

## 📌 Project Summary

This project explores Zomato’s global restaurant data to uncover trends and business insights using Python and data visualization.

🔍 Key Questions Answered:
- Which countries have the most restaurants on Zomato?
- What are the most popular cuisines?
- What rating patterns do we observe?
- Is there a link between price and customer satisfaction?
- How widely are delivery and booking features used?

---

## 🧠 Objective

🎯 To derive real, actionable insights from Zomato’s public restaurant data using:
- Data Cleaning 🧹
- Data Merging 📎
- Exploratory Data Analysis 🔍
- Visual Storytelling 📊

---

## 🛠️ Tools & Technologies

| Category       | Tools Used                                |
|----------------|--------------------------------------------|
| Programming    | Python 3.9                                 |
| Libraries      | Pandas, NumPy, Matplotlib, Seaborn         |
| Environment    | Jupyter Notebook                           |
| Data Sources   | `zomato.csv`, `Country-Code.xlsx`          |

---

## 📂 Dataset Details

**`zomato.csv`**
- Restaurant names, cuisines, ratings, cost, delivery status, location

**`Country-Code.xlsx`**
- Mapping of numerical country codes to country names

---

## 📊 Key Explorations & Insights

### 🌍 Country-Wise Restaurant Distribution
- India 🇮🇳 has the highest number of Zomato listings
- Followed by USA 🇺🇸 and UAE 🇦🇪
- Zomato is primarily active in a few target markets

### 🍱 Cuisine Analysis
- Most popular: North Indian, Chinese, Fast Food
- Regional cuisines dominate local listings

### ⭐ Rating Distribution
- Majority ratings fall between 3.0 and 4.5
- Ratings below 2.5 are rare, showing positive bias

### 💸 Price vs Rating
- No direct correlation: expensive doesn’t always mean better-rated
- Many affordable restaurants have excellent reviews

### 📦 Online Delivery & Table Booking
- Online ordering is heavily used in India
- Table booking is enabled in fewer restaurants globally

---

## 🧪 Code Highlights

```python
import pandas as pd

# Load main data
zomato = pd.read_csv("zomato.csv", encoding='latin-1')
countries = pd.read_excel("Country-Code.xlsx")

# Merge country names
df = pd.merge(zomato, countries, on='Country Code', how='left')

# Top 5 countries by restaurant count
df['Country'].value_counts().head()
