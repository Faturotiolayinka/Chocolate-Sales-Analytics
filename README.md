 # *📄 Chocolate Sales Analytics & Predictive Modeling Report*

*🔍 1. Objective*
To analyze historical chocolate sales data, uncover business insights, and build predictive models that estimate future sales behavior based on product, region, shipment volume, and salesperson performance.

*📊 2. Data Overview*
Source: Chocolate Sales.csv

Rows: 1,094 entries

Features: Sales Person, Country, Product, Date, Amount (cleaned to int64), Boxes Shipped

Quality: No missing data; 'Amount' column cleaned for modeling

*🌍 3. Exploratory Insights*
Country Performance: UK and Australia led in average sales amount

Monthly Trends: Sales spikes occurred around holidays (Valentine’s, December)

Product Leaders: Peanut Butter Cubes and 85% Dark Bars were top earners

Salesperson Impact: Jehu Rudeforth and Jan Morforth were top revenue generators

Correlation: Moderate positive relationship between Amount and Boxes Shipped

Cluster Analysis: Countries grouped into 3 clusters:

Cluster 0: High sales and shipment

Cluster 1: Moderate consumption

Cluster 2: Low activity markets

*🤖 4. Modeling Summary*
Model	Features Used	R² Score	MSE	Comments
Linear Regression	Boxes Shipped only	-0.00	16.3M	Baseline model; very weak correlation
Multi-feature Regression	Boxes Shipped, Product, Country, Sales Person (one-hot)	-0.06	17.2M	Added categorical depth; minimal improvement
Random Forest Regressor	Same as above	-0.18	19.2M	Captured nonlinear patterns; overfitting observed
Tuned RF (GridSearchCV)	RF optimized (depth=10, split=5, trees=200)	-0.09 CV	—	Still underperforming; needs more granular data

*📌 5. Feature Importance (Top Drivers)*
Based on Random Forest model:

Most Impactful:

* Product type

* Country

Least Impactful:

* Salesperson name

* Boxes Shipped

*📊 6. Visual Diagnostics*
Actual vs Predicted: Scatter plot showed significant dispersion — model predictions were inconsistent across value range

* Feature Importance Bar Chart: Product and Country dominated influence on predictions
