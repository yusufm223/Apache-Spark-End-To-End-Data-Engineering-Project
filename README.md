# IPL Data Analysis Project

This project leverages PySpark to perform detailed analysis on the IPL dataset stored in Amazon S3. The goal is to gain actionable insights into player performance, team statistics, and match dynamics using large-scale data processing and visualization techniques.

---

## Dataset Overview

The project utilizes multiple CSV files containing IPL-related data:

- **Ball_By_Ball.csv**: Detailed ball-by-ball data for all IPL matches.
- **Match.csv**: Match-level information, including teams, venues, and results.
- **Player.csv**: Details about players, such as batting style, bowling skills, and country.
- **Player_Match.csv**: Player-level statistics and match outcomes.
- **Team.csv**: Team-level information.

---

## Key Features and Functionality

### 1. **Data Ingestion and Schema Definition**
- Loaded datasets from S3 into Spark DataFrames.
- Defined schemas using PySpark `StructType` to ensure accurate parsing and data validation.

### 2. **Data Preprocessing**
- Cleaned and normalized datasets:
  - Removed null values and replaced missing attributes with default values (e.g., "unknown").
  - Standardized player names by removing special characters and converting to lowercase.
- Filtered out invalid deliveries (e.g., wides and no-balls) to focus on meaningful gameplay analysis.

### 3. **Data Analysis**

#### SQL Queries and Transformations
- **Top Scoring Batsmen by Season**: Identified the highest run-scorers per season using SQL joins and aggregations.
- **Economical Bowlers in Powerplay**: Calculated the average runs conceded per ball by bowlers during the first six overs.
- **Toss Impact on Match Outcomes**: Analyzed how winning the toss influences match results.
- **Average Runs in Wins**: Evaluated batsmen's average runs scored in matches won by their teams.
- **Scores by Venue**: Computed the average and highest scores at each IPL venue.

#### PySpark Transformations
- Utilized window functions to calculate:
  - Running total of runs scored in each innings.
  - Aggregated metrics like total runs and average runs per match and inning.
- Created conditional flags for high-impact deliveries (e.g., wickets or sixes).

### 4. **Data Visualization**
- Used **Matplotlib** and **Seaborn** for visualizing insights:
  - **Economical Bowlers**: Bar chart of average runs per ball in powerplay overs.
  - **Toss Impact**: Countplot of match outcomes based on toss results.
  - **Venue Analysis**: Bar chart showing average and maximum scores by venue.
  - **Dismissal Types**: Visualization of the frequency of different dismissal types.

### 5. **Dynamic Columns and Categorization**
- Added dynamic and derived columns:
  - `veteran_status`: Classified players as "Veteran" or "Non-Veteran" based on age.
  - `win_margin_category`: Categorized win margins into "High", "Medium", and "Low".
  - `years_since_debut`: Calculated years since a player’s debut.

---

## Technologies Used
- **PySpark**: For large-scale data processing, SQL queries, and transformations.
- **Amazon S3**: For data storage and retrieval.
- **Matplotlib and Seaborn**: For data visualization and presentation.
- **Databricks Notebooks**: For development and interactive analysis.

