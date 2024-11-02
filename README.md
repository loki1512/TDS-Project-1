# GitHub Users & Repositories Analysis in Boston:100

## Project Overview
This project aims to analyze GitHub users from Boston who have over 100 followers and their public repositories. The data was collected using the GitHub API and explored for various insights related to user activity, repository features, and correlations among key attributes.

## Project Steps

### 1. Data Collection
- **API Used**: GitHub REST API
- **Endpoints**:
  - `/search/users`: To gather users in Boston with over 100 followers.
  - `/users/{username}`: To collect detailed user information.
  - `/users/{username}/repos`: To fetch up to 500 of the most recent public repositories for each user.
- **Data Fields Extracted**:
  - **Users (`users.csv`)**: `login`, `name`, `company`, `location`, `email`, `hireable`, `bio`, `public_repos`, `followers`, `following`, `created_at`.
  - **Repositories (`repositories.csv`)**: `login`, `full_name`, `created_at`, `stargazers_count`, `watchers_count`, `language`, `has_projects`, `has_wiki`, `license_name`.
## Analysis Breakdown

### 1. Data Preparation and Cleaning
- **Data Loading**: The `users.csv` and `repositories.csv` files are loaded for analysis.
- **Company Name Cleaning**: The `company` column in the user data is cleaned by removing leading spaces, `@` symbols, and converting text to uppercase for consistency.

### 2. Key Findings

#### Question 1: Top 5 Users by Number of Followers
The analysis identifies the top 5 users based on their follower counts, showcasing the most followed individuals within the dataset.

**Result**: `brianyu28, PatrickAlphaC, KeithGalli, CharlesCreativeContent, timbl`

#### Question 2: 5 Earliest Registered Users
The project finds the first 5 users to register their accounts, providing insight into early adopters within the dataset.

**Result**: `evan, dpickett, tel, radical, joshuaclayton`

#### Question 3: Top 3 Most Popular Licenses
This step identifies the most frequently used licenses for repositories, indicating preferred licensing practices among users.

**Result**: `mit, other, apache-2.0`

#### Question 4: Most Common Company
The most frequently appearing company name among users is determined, revealing common professional affiliations.

**Result**: `UNKNOWN`

#### Question 5: Most Popular Programming Language
The analysis finds the most common programming language across repositories, showcasing the prevalent language used.

**Result**: `javascript`

#### Question 6: Second Most Popular Language After 2020
Among repositories created after 2020, the second most popular programming language is identified.

**Result**: `unknown`

#### Question 7: Language with the Highest Average Stars
The project calculates the average number of stars per programming language to find which language's projects receive the most attention on average.

**Result**: `handlebars`

#### Question 8: Top 5 Users by Leader Strength
A custom metric, `leader_strength`, is computed based on the number of followers and following count. The top 5 users by this metric are identified.

**Result**: `nikomatsakis, ccoenraets, KeithGalli, rstudio, pluskid`

#### Question 9: Correlation Between Followers and Public Repositories
The correlation between the number of followers and public repositories for users is measured, revealing how these two attributes relate.

**Result**: `0.168` (low positive correlation)

#### Question 10: Regression Slope of Followers on Repositories
A linear regression is used to calculate the slope, showing how much an increase in the number of public repositories is associated with a change in followers.

**Result**: `1.191`

#### Question 11: Correlation Between Projects and Wiki Enabled
The correlation between repositories having projects enabled and wikis enabled is determined.

**Result**: `0.425` (moderate positive correlation)

#### Question 12: Difference in Average Following (Hireable vs. Non-Hireable)
The project compares the average `following` count for users marked as hireable versus those who are not.

**Result**: `112.041` (hireable users follow more, on average)

#### Question 13: Regression Slope of Followers on Bio Word Count
A regression model is used to evaluate how the word count in user bios relates to their number of followers.

**Result**: `-3.535` (negative slope indicating more words in bio do not correlate positively with followers)

#### Question 14: Top 5 Users by Weekend Repo Creation
The analysis identifies the top 5 users with the most repositories created on weekends, indicating weekend activity levels.

**Result**: `rwaldron, bahmutov, PatrickAlphaC, nikomatsakis, migueldeicaza`

#### Question 15: Difference in Email Sharing (Hireable vs. Non-Hireable)
The project measures the difference in the proportion of users who share their email addresses based on their hireable status.

**Result**: `0.113` (hireable users are more likely to share their emails)

#### Question 16: Most Common Surname
The most common surname among users is identified, providing a demographic insight.

**Result**: `Williams`
### 2. Data Cleaning
- **Company Field**: Trimmed whitespace, removed leading '@' symbol, and converted to uppercase.
- **Null Values**: Represented as empty strings.

### 3. Data Exploration
- **Initial Analysis**:
  - **Top Followers**: Users like `brianyu28` and `PatrickAlphaC` had significantly higher follower counts.
  - **High Star Repositories**: Projects like `PatrickAlphaC/hardhat-security-fcc` had high star counts.
- **Unique Findings**:
  - **Rare Licenses**: MPL-2.0, LGPL-2.1, and CC-BY-SA-4.0 appeared rarely.
  - **Niche Programming Languages**: Minimal usage of Clojure, Batchfile, and Squirrel.
- **Bio Analysis**:
  - A histogram of bio word counts revealed that most users had short bios, usually between 0–5 words.
- **Active Days**: Repository creation was most frequent on Thursdays and Fridays.

### 4. Analysis & Insights
- **Leader Strength**: Defined as `followers / (1 + following)`, identifying `brianyu28` and `KeithGalli` as strong leaders.
- **Languages Used**: Python, JavaScript, and other popular languages were common, while niche languages were observed.
- **Repository Characteristics**:
  - Found users with many repositories but low star counts.
  - Explored trends of enabling projects and wikis together.
- **Regression Analysis**:
  - Determined the impact of bio word count on follower count.
  - Checked if hireable users shared email addresses more frequently.
- **Statistical Correlations**:
  - Between followers and public repositories.
  - Between enabling projects and wikis.

### 5. Interesting Findings
- **Bio and Followers**: No strong correlation was found between longer bios and higher follower counts.
- **Weekend Creation**: Users who created repositories on weekends were identified, providing insights into their activity habits.
- **Hireable Users**: More likely to share their email addresses compared to non-hireable users.

### 6. Visualizations
- Histogram of bio word counts showing distribution.
- Lists highlighting users with the highest follower count and leader strength.
- Breakdown of repository star counts and licenses.

### 7. Challenges
- **Rate Limits**: Overcame GitHub API rate limits using token-based authentication and request pacing.
- **Data Volume**: Efficient handling of user and repository data due to its large size.

### 8. How to Reproduce
1. Clone the repository.
2. Use the provided scripts to access GitHub API data.
3. Generate CSV files and run the analysis using Python or your preferred tool.

### 9. Next Steps
- **Enhancements**:
  - Adding more complex user behavior analysis.
  - Exploring user collaborations.
- **Recommendations for Developers**:
  - Optimize repository visibility by focusing on popular license types.
  - Regularly update projects to attract more watchers and stars.

