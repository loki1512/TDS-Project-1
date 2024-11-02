# GitHub Users & Repositories Analysis in Boston

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

