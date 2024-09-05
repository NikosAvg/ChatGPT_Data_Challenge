# Report on Data Cleaning and Sentiment Analysis

## 1. Data Cleaning

The data cleaning process is a crucial step to prepare the dataset for any analysis. The steps followed in the provided document are:

1. **Loading the Dataset**:
   - The dataset, named `customer_reviews.csv`, was loaded using `pandas`. The initial inspection showed that the dataset contains no missing values, with columns including `ReviewID`, `ProductID`, `Rating`, `Review`, and `ReviewDate`.

2. **Handling Date Formats**:
   - The `ReviewDate` column contained dates in mixed formats. A custom function `formatDate` was implemented to standardize these dates into the `YYYY-MM-DD` format. Additionally, `pandas`'s built-in function `to_datetime` was used for date formatting.

3. **Checking for Duplicates**:
   - The dataset was checked for duplicate records using the `duplicated()` function, and no duplicates were found.

4. **Cleaning Columns**:
   - After formatting the dates, unnecessary columns (`ReviewDate_formated_1` and `ReviewDate_formated_2`) were removed. The cleaned dataset was then saved as `customer_reviews_cleaned.csv`.

This systematic approach ensures that the data is consistent and ready for analysis, particularly focusing on resolving issues with date formats and removing redundant information.

## 2. Sentiment Analysis

Following the data cleaning, sentiment analysis was conducted on the `customer_reviews_cleaned.csv` dataset. The steps and methods used are as follows:

1. **Loading and Preprocessing**:
   - The cleaned dataset was loaded, and the `ReviewID` column was dropped as it was not necessary for the analysis. The dataset contains reviews, ratings, and review dates.

2. **Exploratory Data Analysis**:
   - The unique products were identified, and their distribution was visualized using histograms. The dataset included reviews for 9 unique products.

3. **Sentiment Analysis**:
   - Sentiment scores were calculated for each review using the `VaderSentiment` library. A custom function, `sentiment_scores`, was applied to the `Review` column to categorize sentiments as Positive, Negative, or Neutral.

4. **Visualization of Sentiments and Ratings**:
   - For each product, histograms were created to visualize the distribution of ratings and sentiments.
   - Time series plots were generated to visualize how sentiments and ratings evolved over time for each product.

5. **Correlation Analysis**:
   - The relationship between ratings and sentiments was analyzed using Pearson correlation. The correlations were computed for each product, and results were visualized using bar charts.

   The correlation results varied significantly across products, with some showing a positive correlation between ratings and sentiment (e.g., ProductID 3 with 0.663) and others showing a negative or weak correlation (e.g., ProductID 5 with -0.502).
