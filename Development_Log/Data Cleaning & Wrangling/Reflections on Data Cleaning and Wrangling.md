In the data cleaning and wrangling section, I learned a lot. Previously, I only knew how to replace null values using simple techniques like the mean, median, or mode, and I was unsure whether to handle missing values before or after detecting outliers. Through this hands-on project, I gained a deeper understanding of different types of missing data—MCAR, MAR, and MNAR—and learned how the percentage of missing values can help determine which imputation technique is most appropriate.

I also discovered that mean, median, and mode are not the only methods for handling missing data. Techniques like K-NN, regression, and MICE can be used depending on the nature of the missingness, allowing for more accurate and meaningful replacements.

In addition, I used to think visualization was only relevant in the data visualization stage, but now I understand its importance in the cleaning process as well. Tools like histograms and boxplots can help detect outliers and guide our choice of imputation strategy.

One important lesson I want to remember is to always check for class imbalance before modeling. In this project, we noticed a 0.67 success rate, which could lead to misleading model performance. If my model performs poorly in the future, I should consider whether imbalance is the cause. This means I should not rely solely on accuracy, but also examine precision and recall to understand how well the model performs, especially on the minority class.

