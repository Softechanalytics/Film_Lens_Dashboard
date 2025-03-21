
# MovieLens Power BI Analysis
This repository contains a Power BI report (Movieslen.pbix) built on the popular MovieLens dataset. The project provides interactive visualizations and insights into movie ratings, user demographics, and genre trends.

## Table of Contents
- [Overview](#overview)
- [Data Dictionary](#DataDictionary)
- [Project Structure](#ProjectStructure)
- [Key Features & Pages](#Keyfeatures&pages)
- [Getting Started](#GettingStarted)
- [Usage](#Usage)
- [Technical Details](#TechnicalDetails)
- [Insights & Highlights](#Insights&Highlights)
- [Contributing](#Contributing)
- [License](#License)
- [Overview](#Overview)

## This Power BI dashboard explores user ratings from the MovieLens dataset. It includes:

- User Demographics (age, gender, occupation, location)
- Movie Information (title, genre, release year)
- Ratings Data (scores, timestamps)
- Genre & Decade Groupings for better categorization

The analysis addresses several questions, such as:

1. Counting movies, distinct genres, and total users
2. Displaying gender distribution among users
3. Analyzing average ratings across genres (including grouped genres)
4. Showing average ratings via gauge charts and stacked visuals
5. Mapping user locations and demographics
6. Exploring average ratings across age groups and professions
7. Visualizing top N movies and genres with toggling charts (via bookmarks)
8. Creating scatter plots to compare average rating vs. age groups, plus year-based rating analysis

## Data Dictionary
A detailed Data [Dictionary](#Dictionary) is provided, but here’s a quick reference:

### rating.csv

- user_id: Unique ID for each user
- movie_id: Unique ID for each movie
- rating: Rating score given by the user (1–5)
- timestamp: Time of the rating (Unix timestamp)

### movie.csv

- movie_id: Unique ID for each movie
- movie_name: Movie title
- year: Release year of the movie
- genre: Genres associated with the movie (separated by a pipe symbol if multiple)

### user.csv

- user_id: Unique ID for each user
- age: Age of the user
- gender: Gender of the user (M or F)
- occupation: Occupation of the user
- zipcode: ZIP or postal code for the user’s location

<b>Note:</b> For users under 18, age is imputed using the median age of others with the same occupation.


## Key Features & Pages
### 1. Intro Page

- High-level metrics: total movies, total genres, total users.
- Gender distribution (donut chart).
- Overall average rating (gauge chart).

### 2. Movie Distribution Page

- Bar charts showing total movies by genre, broken down by gender.
- Map visualization for user distribution across the globe.
-Demographic charts (e.g., users by age group, occupation).

### 3. Avg Rating Page

- Average rating vs. age group scatter plot.
- Bar/line charts comparing average ratings by genre, decade, or year.
- Matrix visual displaying average ratings across professions and age groups.
Each page includes slicers (e.g., decade, occupation, genre, age group) for interactive filtering.

## Getting Started
1. Clone or Download the Repository

bash
Copy
git clone https://github.com/your-username/movielens-powerbi.git
cd movielens-powerbi

2. Open the Power BI File

- LaunchPower BI Desktop.
- Open Movieslen.pbix.
- 
3. Data Refresh (Optional)

- If you have the raw CSV files, ensure they’re correctly referenced in the Power BI file’s Power Query settings.
- Refresh to pull the latest data if needed.

## Usage
- Navigate Between Pages: Use the bottom tabs (Intro, Movie Distr., Avg Rating) or any custom buttons/bookmarks to switch views.
- Apply Filters & Slicers: Narrow down insights by age group, occupation, genre, or decade.
- Drill-Down in Visuals: Some visuals allow drill-down for more granular data (e.g., sub-genres or year breakdowns).
- Bookmarks & Buttons: Toggle between different visuals (like Top N Movies vs. Genres) with the provided bookmarks.

## Technical Details
#### Data Modeling:

![image alt](https://github.com/Softechanalytics/Film_Lens_Dashboard/blob/bfd461be0b65ec2e37260d2d6d459302fa5e777e/model.png)

- Relationships between rating, movie, and user tables on matching keys (e.g., user_id, movie_id).
- No circular references; star schema approach.

#### Calculated Columns & Measures:
- Age_Group classification using SWITCH() or nested IF.
- Genre Grouping using calculated columns or Power Query transformations.
- Decade Grouping for movie release years.
- Median Age Imputation for users under 18, grouped by occupation.
- Average Rating measure for visuals (e.g., AvgRating = AVERAGE(rating[rating])).

#### Bookmarks & Buttons:

- Used for toggling visuals (e.g., top movies vs. top genres).
### Insights & Highlights
- Most Popular Genres: Identifies which genre groups have the highest average ratings.
- User Demographics: Shows the gender, age group, and occupation breakdown, including geographical distribution via maps.
- Age vs. Rating: Discovers how user age correlates with average rating.
- Occupation & Age-Group Matrix: Reveals rating preferences by profession and age bracket.
- Historical Trends: Explores how movies from different decades are rated.

### Contributing
- Contributions, suggestions, and improvements are welcome!

### Fork the repository
- Create a new branch: git checkout -b feature/your-feature
- Commit your changes: git commit -m "Add some feature"
- Push to your branch: git push origin feature/your-feature
- Open a pull request in GitHub

### License
- This project is licensed under the MIT License. You’re free to modify and distribute it under the terms of this license.

### Screenshot Previews

![image alt](https://github.com/Softechanalytics/Film_Lens_Dashboard/blob/19903f5fc8eef224c955ff293bf0ae31f14a99dd/screen1.png)

![image alt](https://github.com/Softechanalytics/Film_Lens_Dashboard/blob/19903f5fc8eef224c955ff293bf0ae31f14a99dd/screen2.png)

![image alt](https://github.com/Softechanalytics/Film_Lens_Dashboard/blob/19903f5fc8eef224c955ff293bf0ae31f14a99dd/screen3.png)



