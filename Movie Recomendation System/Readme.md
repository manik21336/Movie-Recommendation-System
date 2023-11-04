# Movie Recommendation System README

## Overview
This README accompanies a Python script that demonstrates the creation of a basic movie recommendation system using the 100k MovieLens dataset. The system provides recommendations based on user ratings for different movies. The workflow includes data loading, preprocessing, exploratory data analysis, and generating movie recommendations.

## Dependencies
- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Dataset
The dataset is loaded from two files:
- `u.data`: Contains 100,000 ratings by 943 users on 1682 items.
- `u.item`: Contains details for each movie/item.

The columns used from `u.data` are `USER_ID`, `ITEM_ID`, `RATING`, and `TIMESTAMP`. The `u.item` file is used to retrieve the movie titles.

## Usage

### Data Preprocessing:
1. Import warnings and suppress warnings using `warnings.filterwarnings('ignore')`.
2. Load the ratings data from `u.data` and movie titles from `u.item`.
3. Merge the datasets on `ITEM_ID` to associate ratings with movie titles.

### Exploratory Data Analysis (EDA):
1. Use Seaborn to set the plotting style.
2. Generate descriptive statistics and visualizations (histograms and joint plots) for ratings to understand the distribution.

### Building the Recommendation System:
1. Pivot the data to create a matrix with `USER_ID` as rows, `TITLE` as columns, and `RATING` as values.
2. Calculate the mean rating and count of ratings for each movie.
3. Sort movies based on the number of ratings to identify the most popular ones.

### Generating Recommendations:
1. Define a function `predictMovies(movie_name)` that:
   - Computes the pairwise correlation of the specified movie's ratings with all other movies' ratings.
   - Creates a correlation matrix and filters movies based on a minimum number of ratings.
   - Returns the movies with the highest correlation as recommendations.

### Example Usage:
- Call `predictMovies('Star Wars (1977)')` to get recommendations based on the movie "Star Wars (1977)".

## Running the Script
Execute the script in a Python environment after installing the required dependencies. Call the `predictMovies()` function with the title of a movie to get similar movie recommendations.

## Note
The recommendation system is very basic and does not account for many factors that a more sophisticated system might include, such as user-specific preferences, contextual data, or content-based filtering. It is meant for educational purposes and as a simple demonstration of collaborative filtering.
