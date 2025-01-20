# Book Sales Prediction Project

## Project Overview  
This project focuses on building a predictive model to forecast book sales using a dataset sourced from [Kaggle](https://www.kaggle.com/datasets/thedevastator/books-sales-and-ratings/download?datasetVersionNumber=2). The dataset includes essential information about books, such as genre, author rating, book average rating, sale price, publishing year, book ratings count, sales rank, and units sold. By leveraging machine learning techniques, particularly Random Forest Regressor, the project aims to accurately predict gross sales and provide insights into factors influencing book sales.

---

## Data Understanding  
The dataset consists of the following key columns:

1. **Publishing Year**: The year when the book was published.  
2. **Book Name**: The title given to identify the book commercially.  
3. **Author**: Full name of the writer who authored the book.  
4. **language_code**: Code indicating the language used to write the book content.  
5. **Author Rating**: A measure of expertise and popularity for the author based on past work.  
6. **Book Average Rating**: The statistical mean of ratings assigned by individual readers.  
7. **Book Ratings Count**: Total number of ratings received from readers for this book.  
8. **Genre**: Style, intended audience, or fictional category reflecting the book’s content.  
9. **Gross Sales**: Total monetary revenue obtained through the sale of this book during the analysis period.  
10. **Publisher Revenue**: Portion of gross sales earned specifically by the publisher company.  
11. **Sale Price**: Retail price at which each unit of the book is sold.  
12. **Sales Rank**: Ranking for this book across other books based on units sold over a recent period.  
13. **Publisher**: Name of the organization handling publishing, marketing, and distribution.  
14. **Units Sold**: Number of copies sold of this specific book during the analysis timeframe.

---

## Data Cleaning  
To prepare the data for analysis, the following steps were implemented:
1. Eliminated rows containing null values.
2. Ensured consistent formatting and appropriate data types for each column.

---

## Feature Engineering  
Feature engineering played a critical role in improving model performance. The following new features were derived from the dataset:

1. **Book Age**: Calculated as `2025 - Publishing Year`. Captures the age of the book in years.
2. **Rating Density**: Derived as `Book Ratings Count / Book Average Rating`. Represents the concentration of ratings.
3. **Is_Amazon**: Binary variable indicating whether a book is sold on Amazon (1) or not (0).

These features were selected based on their potential to provide additional explanatory power to the predictive model.

---

## Normalized Database Creation  
The dataset was transformed into a normalized relational database with five tables:

1. **Books Table**: Details such as Book Name, Publishing Year, Book Average Rating, Book Ratings Count, and Genre.  
2. **Authors Table**: Contains Author Name and Author Rating.  
3. **Sales Data Table**: Includes Gross Sales, Publisher Revenue, Sale Price, Units Sold, and Sales Rank.  
4. **Publishers Table**: Contains Publisher-specific details.  
5. **Languages Table**: Includes language codes used in the books.

### Data Insertion  
1. Unique entities (authors, publishers, languages) were identified and inserted into respective tables.  
2. References between tables (e.g., book IDs, author IDs) were established to maintain database integrity.  
3. Sales data were linked with the book IDs for analysis.

---

## Exploratory Data Analysis (EDA)  
EDA was conducted using SQL queries and Python to:
- Understand trends, distributions, and correlations within the data.
- Identify potential predictor variables for the machine learning models.

### Data Visualization  
Key trends and relationships were visualized using charts and graphs, enhancing understanding and accessibility of the findings for stakeholders.

---

## Predictions Using Machine Learning  
Three machine learning models were applied to predict gross sales:

1. **Random Forest Regressor**  
   - **R² Score**: 0.645  
   - **RMSE**: 1506.40  
   - Best performance among the tested models, capable of capturing complex, non-linear relationships.

2. **Linear Regression**  
   - **R² Score**: 0.33  
   - **RMSE**: 2069.65  
   - Limited ability to explain variance, indicating inadequacy for this dataset.

3. **Logistic Regression** (Binary Classification: Above/Below Median Sales)  
   - **AUC Score**: 0.656  
   - **Accuracy**: 54%  
   - Moderate performance, useful for binary classification but less effective for detailed sales prediction.

---

## Conclusion  
The **Random Forest Regressor** emerged as the most suitable model for predicting gross sales, offering the best balance of accuracy and error minimization. Linear regression's lower R² score highlights its inability to capture non-linear patterns in the data, while logistic regression provided moderate insights into classification but lacked precision for regression tasks.

### Recommendations  
1. Utilize Random Forest for future predictions of gross sales in the publishing domain.  
2. Consider adding more features, such as marketing expenditure or seasonal trends, for further model enhancement.  
3. Explore hyperparameter tuning to further optimize the Random Forest model.

---

## Acknowledgments  
We thank [Kaggle](https://www.kaggle.com/datasets/thedevastator/books-sales-and-ratings/download?datasetVersionNumber=2) for providing the dataset that made this project possible.
