# ⚽ International Football EDA (Pandas Project)

A hands-on Exploratory Data Analysis (EDA) project built to break out of "tutorial hell" by applying data manipulation, conditional filtering, datetime mastery, and statistical validation to real-world sports data from scratch.

## 📊 About the Dataset
The analysis uses the **International Football Results from 1872 to 2026** dataset from Kaggle. It contains over 49,000 historic international match results.

**Key Features Analyzed:**
* `date`: Datetime tracking of matches across eras.
* `home_team` / `away_team`: Competing international squads.
* `home_score` / `away_score`: Full-time match results.
* `tournament`: Competition types (FIFA World Cup, Friendlies, Regional Cups).
* `neutral`: Boolean flag indicating if the match venue was neutral.

---

## 🚀 Key Learning Objectives & Achievements

### 1. Data Cleaning & Structural Pipeline
* Loaded and inspected large-scale tabular data using `.head()` and `.info()`.
* Converted raw object-string timestamps into functional `datetime64` objects using `pd.to_datetime()`.
* Engineered a new computed feature: `Total_goals` (`home_score + away_score`).

### 2. Slicing, Sorting, & Historical Analysis
* Isolated major global events by conditionally filtering for `'FIFA World Cup'` matches.
* Tracked down the single highest-scoring match in World Cup history by chaining `.sort_values()` and `.head(1)` (Austria 7–5 Switzerland, 1954).

### 3. Aggregations & Era Comparison
* Evaluated international match density across world cities using `.value_counts()`.
* Discovered high-scoring tournament distributions globally using grouped calculations: 
  ```python
  df.groupby('tournament')['Total_goals'].mean().sort_values(ascending=False)
  ```
* Conducted seasonal analysis on a modern subset (post-2000), using datetime parsing (.dt.month) to discover that December international fixtures slightly edge out June fixtures in average goals per match.
### 4. Statistical Validation of Home Advantage
* Used multi-condition filtering to segment matches into true home matches (neutral == False) and neutral territory matches (neutral == True).

* Tabulated side-by-side data distributions using custom Python dictionaries passed into pd.DataFrame().

* The Insight: Statistically proved the physical reality of "Home Field Advantage." Home teams average ~1.8 goals per game at home compared to ~1.2 for away teams, a delta that completely vanishes to a balanced ~1.5 vs ~1.5 when games shift to neutral grounds.


## 5. Data Visualization
* Concluded the exploratory phase by rendering data frames directly into clean, insightful visual layouts using matplotlib.

* Generated a horizontal bar plot showcasing the top 10 highest-scoring international football tournaments in history
