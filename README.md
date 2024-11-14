# FIFA Dataset Exploratory Data Analysis (EDA) 🎮⚽

## Overview
This project performs an **Exploratory Data Analysis (EDA)** on a FIFA dataset to extract valuable insights into football players' attributes, financial statistics, and club performance. The analysis covers various aspects like player ratings, wage groups, and club comparisons to uncover trends in the football world.

## 🔍 Dataset Description
The FIFA dataset includes detailed information on football players, such as:
- **Player Attributes**: Overall rating, potential, age, and preferred foot.
- **Financial Details**: Wages, market value, and release clauses.
- **Club Information**: Club names, positions played, and contract duration.

## Project Structure
- **Data Loading and Cleaning**: Initial data exploration, handling missing values, and standardizing data formats.
- **Descriptive Analysis**: Summary statistics of player attributes, including age, overall ratings, potential, and financial details like wages and market values.
- **Position-Wise Analysis**: Examination of player ratings and financial trends based on playing positions.
- **Wage Group Analysis**: Categorization of players into different wage groups to analyze wage distribution.
- **Club Analysis**: Identification of top clubs based on average player ratings and total wage expenditures.
- **Correlation Analysis**: Heatmap visualization of correlations among key player attributes.
  
## Key Insights
1. **Top Positions**: Central Midfielders (CM) and Strikers (ST) have some of the highest average ratings.
2. **Wage Distribution**: A significant number of players fall into the 'Medium' wage group, with fewer players in the highest wage categories.
3. **Top Clubs**: Elite clubs like Manchester City and FC Barcelona exhibit high average player ratings and substantial wage bills, reflecting their financial power.
4. **Correlation Analysis**: A strong correlation exists between a player's overall rating and their market value.

## Prerequisites
To run this project locally, you need:
- Python 3.x
- Jupyter Notebook
- Libraries: Pandas, NumPy, Matplotlib, Seaborn

## 📊 Exploratory Data Analysis (EDA) Steps

### 1. **Data Cleaning and Preprocessing**
- Converted financial columns (e.g., wage, value) to numerical formats.
- Handled missing values and standardized column names.
- Created new features, including **Wage Group** for analysis based on player wages.

### 2. **Descriptive Analysis**
- Generated summary statistics for key attributes like age, overall rating, and potential.
- Visualized distributions using histograms and boxplots to identify outliers.

### 3. **Position-Wise Analysis**
- Analyzed players based on their field positions (e.g., Striker, Midfielder).
- Compared average ratings and financial statistics across different positions.

**Sample Code:**
```python
# Analyzing players by position
position_avg = data.groupby('position')['overall'].mean().sort_values(ascending=False)
plt.figure(figsize=(12, 6))
sns.barplot(x=position_avg.index, y=position_avg.values)
plt.title('Average Overall Rating by Player Position')
plt.xticks(rotation=90)
plt.show()
```

### 4. **Wage Group Analysis**
- Categorized players into four wage groups: Low, Medium, High, and Very High.
- Analyzed the distribution of players across wage groups and their impact on overall ratings.

**Sample Code:**
```python
# Wage Group Analysis
wage_bins = [0, 5000, 50000, 200000, data['wage'].max()]
wage_labels = ['Low (<5K)', 'Medium (5K-50K)', 'High (50K-200K)', 'Very High (>200K)']
data['wage_group'] = pd.cut(data['wage'], bins=wage_bins, labels=wage_labels)

# Count of players in each wage group
plt.figure(figsize=(10, 6))
sns.countplot(x='wage_group', data=data)
plt.title('Player Distribution by Wage Group')
plt.show()
```

### 5. **Club Analysis**
- Ranked clubs based on average player ratings and total wage expenditures.
- Identified top-performing clubs with elite players.

### 6. **Correlation Analysis**
- Created a heatmap to explore correlations between numerical features like age, overall rating, potential, wage, and value.

**Sample Code:**
```python
# Correlation Heatmap
corr_matrix = data[['age', 'overall', 'potential', 'wage', 'value']].corr()
plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Correlation Matrix of FIFA Dataset Features')
plt.show()
```

## 📈 Visualizations
Key visualizations included:
- **Heatmaps**: Displaying correlations among player attributes.
- **Scatter Plots**: Analyzing relationships between overall rating and wages.
- **Bar Plots**: Showing average player ratings by club and position.

## 🎯 Key Insights
- **Top Positions**: Players in central roles (e.g., CM, ST) tend to have higher overall ratings.
- **Wage Distribution**: Majority of players are in the 'Medium' wage group, with top-tier players in the 'Very High' category.
- **Top Clubs**: Elite clubs dominate with high average player ratings and significant financial investments in wages.
- **Correlation Insights**: High correlation between overall rating and market value, indicating the premium placed on player quality.

## 🔍 Conclusion
This EDA of the FIFA dataset provided valuable insights into the distribution of player attributes, wage structures, and club dynamics. The findings highlight key trends in player performance, financial attributes, and their impact on clubs. This analysis could serve as a foundation for more in-depth studies, such as time-series analysis of player ratings over seasons or integrating match performance data.

## 💡 Future Work
- Incorporate additional features like player in-game statistics for deeper insights.
- Extend the analysis to include comparisons across multiple seasons.

## 📬 Contact
Connect with me for feedback, questions, or collaboration opportunities:
- **LinkedIn**: www.linkedin.com/in/deepthy-a-vv1999
- Gmail: deepthydevadasan@gmail.com

## 📜 License
This project is licensed under the MIT License. Feel free to use and modify the code.
