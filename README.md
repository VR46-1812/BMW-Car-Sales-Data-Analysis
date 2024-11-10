# BMW Car Sales Data Analysis

## Overview
This project conducts an in-depth exploratory data analysis (EDA) on a dataset containing information about BMW car sales. Using Python libraries such as `pandas`, `numpy`, `matplotlib`, `seaborn`, and `statsmodels`, this analysis reveals key insights into pricing, mileage, fuel efficiency, and other car characteristics. The project includes data cleaning, visualization, statistical analysis, and data transformation, with the ultimate goal of uncovering trends, patterns, and potential anomalies in the dataset.

## Dataset
The dataset (`bmw.csv`) used in this analysis contains data on various models of BMW cars, with columns representing features such as:
- `model`: Car model name
- `year`: Year of manufacture
- `price`: Price of the car in the dataset
- `mileage`: Distance the car has traveled
- `transmission`: Type of transmission (e.g., manual, automatic)
- `fuelType`: Type of fuel used (e.g., diesel, petrol)
- `tax`, `mpg`, `engineSize`: Additional features describing tax rate, miles-per-gallon (efficiency), and engine size

The dataset is loaded and processed using `pandas`, and visualizations are created with `matplotlib` and `seaborn`.

## Code Features and Functionality

### 1. Data Loading and Initial Inspection
- **Data Import**: Loads the CSV file into a `pandas` DataFrame.
- **Initial Cleaning**: Removes unnecessary whitespace from string data.
- **Overview of Data**: Provides basic information on the dataset (number of columns, missing values, data types) using `df.info()` and `df.describe()`.

### 2. Handling Categorical Data
- **Unique Counts of Categorical Variables**: Counts unique values in categorical columns (`model`, `year`, `transmission`, `fuelType`).
- **Visualization of Category Counts**: Creates count plots for categorical columns to better understand the distribution of car models, years, transmission types, and fuel types.

### 3. Numerical Data Analysis
- **Distribution Analysis**: Uses histograms and KDE (Kernel Density Estimate) plots to explore distributions of numerical features (e.g., `price`, `mileage`, `mpg`).
- **Empirical Cumulative Distribution Function (ECDF)**: Plots the ECDF to compare data distribution with a normal distribution, focusing on `price` and `log(price)`.

### 4. Anomaly Detection and Outlier Handling
- **High Mileage Analysis**: Filters and inspects cars with exceptionally high `mpg` values to identify potential outliers or data inconsistencies.
- **Anomaly Replacement**: Replaces anomalous `mpg` values for specific models (e.g., the BMW i3) with NaN to avoid skewing the analysis.

### 5. Correlation and Relationships
- **Heatmap of Correlation Matrix**: Visualizes correlations between numerical variables, helping to identify potential dependencies or multicollinearity issues.
- **Dummy Variable Encoding**: Converts categorical variables, like `transmission`, into dummy variables for analysis.

### 6. Focused Model Analysis
- **Significant Models Selection**: Filters out models with fewer than 500 records to focus on models with sufficient data points.
- **Point Plots and Regression Analysis**: Creates point plots and regression plots to analyze relationships between features, such as `year` vs. `mileage` and `year` vs. `price`.

### 7. Residual Analysis
- **Residual Plots**: Plots residuals from a linear model to assess model fit and identify patterns in residuals.
- **Log-transformation**: Applies a log transformation to `mileage` to better understand the relationship between mileage and price, given potential skew in mileage distribution.

### 8. Mileage Tier Analysis
- **Mileage Tiers**: Groups cars into tiers based on mileage using `pd.qcut` to facilitate a comparison of value retention across mileage levels.
- **Heatmap of Value Retention**: Visualizes the retention of value for different BMW models over mileage using a heatmap, where values closer to 1 indicate higher retention of initial price.
- **Ranking of Models**: Ranks BMW models by their average value retention across mileage tiers, creating a summary of models with the best value retention.

## Key Functions

- **`col_count(col)`**: Counts unique values in a categorical column and generates a count plot.
- **`plot_kde(cat)`**: Plots a KDE and histogram to show the distribution of a specified numerical column.
- **`plot_ecdf(data, variable)`**: Generates the ECDF for a specified column and compares it with a normal distribution.
- **`get_pointplot(x_col, y_col, hue_col, data)`**: Creates a point plot for the given x, y, and hue columns, facilitating model comparison.
- **`get_regplot(x_col, y_col, data)`**: Generates a regression plot to observe relationships between two numerical columns.

## Visualizations

The project includes various visualizations:
- **Histograms & KDE plots**: Show distribution of key features (price, mileage, etc.).
- **ECDF plots**: Compare cumulative distributions of price and other features with normal distributions.
- **Heatmaps**: Display correlations and value retention across BMW models over mileage.
- **Point plots & Regression plots**: Illustrate relationships between features such as price, mileage, and year of manufacture.

## How to Run the Code

1. Ensure Python is installed with the necessary libraries (`numpy`, `pandas`, `matplotlib`, `seaborn`, `statsmodels`, and `missingno`).
2. Place the dataset (`bmw.csv`) in the same directory as the script or specify its file path.
3. Run the script in Jupyter Notebook, IPython, or any compatible Python environment.

## Requirements

- **Python 3.7+**
- **Required Libraries**: `numpy`, `pandas`, `matplotlib`, `seaborn`, `statsmodels`, `missingno`

## Possible Enhancements

- Integrate more advanced statistical modeling techniques, such as multivariate regression, to model price as a function of mileage, engine size, and other factors.
- Add support for interactive visualizations using libraries like `Plotly` or `Bokeh`.
- Expand the analysis to additional car brands to perform comparative studies.

## License
This project is available under the [MIT License](LICENSE).
