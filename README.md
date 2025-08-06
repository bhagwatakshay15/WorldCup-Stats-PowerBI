# ⚽ FIFA World Cup Statistics (1930-2014)

## 📊 Project Overview  
This Power BI project provides an in-depth statistical analysis of the FIFA World Cup tournaments held between 1930 and 2014. Leveraging data from Kaggle, this interactive dashboard offers a comprehensive view of historical World Cup data, including attendance trends, competition growth, winning nations, qualified countries, and host nations. It aims to deliver insightful visualizations for football enthusiasts and data analysts alike.

**Note**: Data for two World Cup tournaments is missing due to the World War II period (1942 and 1946), which is consistent with the historical record where these tournaments were not held.

![Screen shot](https://github.com/bhagwatakshay15/WorldCup-Stats-PowerBI/blob/main/wc-dashboard.jpg)

## ✨ Features  
The dashboard provides a rich set of interactive visuals to explore World Cup history:

- **Attendance by Country and Year (Map)**: Visualizes tournament attendance across different host countries and years, offering geographical insights into the sport's reach.

- **World Cup Stats (Trophy Visual)**: A central visual highlighting the overall period covered (1930-2014) and the iconic World Cup trophy.

- **Competition Stats by Year (Stacked Bar Chart)**: Tracks the evolution of the tournament over time, showing trends in Goals Scored, Matches Played, and Qualified Teams per year.

- **Qualified Countries (Bar Chart)**: Ranks countries by the number of times they have qualified for the World Cup.

- **World Cup Winners (Donut Chart)**: Displays the distribution of World Cup titles among the winning nations, highlighting dominant teams like Brazil, Italy and Germany.

- **Host Countries (Bar Chart)**: Lists countries by the number of times they have hosted the World Cup.

- **Interactive Filtering**: All visuals are interconnected, allowing users to cross-filter data by selecting specific years, countries, or other data points to reveal related statistics.

## 💾 Data Sources  
The data for this project is sourced from the following Kaggle dataset:

- **Dataset Name**: [FIFA World Cup](https://www.kaggle.com/datasets/abecklas/fifa-world-cup)  

The dataset consists of three primary tables (CSV files) which were imported and modeled in Power BI:

- **WorldCupMatches**: Contains detailed information about each match played in the World Cup, including home and away goals, teams, cities, stadiums, and dates.

- **WorldCups**: Provides summary information for each World Cup tournament, such as the host country, year, winner, runner-up, attendance, goals scored, matches played, and qualified teams.

- **World Cup - Tableau format**: This table contains additional match-level details, including City, Country, Game #, Observation, Opponent, Round, Stadium, Team, Time, and Year.

## 📊 Data Model  
The Power BI data model establishes relationships between the three tables to enable comprehensive analysis.

- **WorldCupMatches** is related to **WorldCups** on the `Year` column (Many-to-One relationship, indicated by * to 1). This links individual match data to the overall tournament details.

- **WorldCups** is related to **World Cup - Tableau format** on the `Year` column (One-to-Many relationship, indicated by 1 to *). This suggests that World Cups is the primary dimension for tournament-level information, linking to more granular details in the third table.

These relationships ensure that filters and interactions across the dashboard flow correctly and calculations are performed accurately.

## 🛠️ Setup and Usage  

To view and interact with this Power BI report:

### Prerequisites  
- Power BI Desktop (latest version recommended)

### Opening the Report  
- Download the `.pbix` file [(WorldCup-Dashboard.pbix)](https://github.com/bhagwatakshay15/WorldCup-Stats-PowerBI/blob/main/WorldCup-Dashboard.pbix) from the repository.  
- Open the file using Power BI Desktop.

### Interacting with the Dashboard  
- Explore the different visuals to gain insights into World Cup history.  
- Click on specific years in the "Competition Stats by Year" chart to filter all other visuals for that year's tournament.  
- Select a country in the "Qualified Countries" or "World Cup Winners" charts to see its performance across other metrics.

## 🔄 Data Preparation & Transformation  
The raw data from Kaggle was imported into Power BI and underwent the following transformations in Power Query to ensure data quality and usability:

- **Data Type Adjustments**: Ensuring columns like Year, GoalsScored, MatchesPlayed, QualifiedTeams, Attendance, HomeGoals, AwayGoals, Team G, and Opponent G are correctly set as numerical types. Dates were parsed correctly.

- **Handling Missing Data**: While two World Cup years are intentionally missing due to historical reasons (World War II), any other missing values within the tables would have been addressed (e.g., replacing nulls, or understanding their implications).

- **Creating Measures/Calculated Columns**: Power BI DAX (Data Analysis Expressions) were used to create the various metrics and aggregations seen in the dashboard, such as the counts for qualified countries, total goals scored, etc.
