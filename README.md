# [AdeventureWork Busssiness Intelligence Dashboard with ANOVA and Product Clustering](https://public.tableau.com/app/profile/sung.jen.yen4583/viz/AdventureWorksMarketAnalysis/Story1?publish=yes)

**Motivation**

1. Extract- Perform 3NF normalization by defining the schema and executing CRUD operations for OLTP systems.
2. Transform- Aggregate normalized tables into a star schema to enhance the capability for OLAP operations.
3. Load- Load into Tableau to conduct business insight analysis, including clustering analysis for product strategy and cross-tab regional performance evaluation.


**Part1: Set up MS SQL Server using Azure SQL Database**

![image](https://github.com/user-attachments/assets/50992940-2db9-438c-9923-86149012100f)

**Part2: Connect to SQL Server Management Studio with Azure Data Studio**

![image](https://github.com/user-attachments/assets/20ab7c4f-bd93-4510-911c-f5b395917fdf)

**Part3: Perform 3NF Normalization on Tables with Predefined Schemas**

![image](https://github.com/user-attachments/assets/a0b162ae-2642-4f5e-8744-0fee46f49310)

"Part4: Insert Data and Write Ad-Hoc Queries for Targeted Analysis"

![image](https://github.com/user-attachments/assets/89801212-7ab1-415b-b975-3ba939277a37)

**Part5: Connect to Tableau Desktop and Denormalize Tables into a Star Schema for Efficient Querying and Analysis**

![image](https://github.com/user-attachments/assets/1e5e2730-1361-4a3d-8024-75914d60a2ad)

![image](https://github.com/user-attachments/assets/bc3c69b8-631c-4010-ad07-c21aeb67a177)

Explanation: Why We Denormalize in OLAP over OLTP

Why Denormalize in OLAP:

Query Performance: OLAP systems often perform complex aggregations and joins over large datasets. Denormalization (combining multiple related tables into fewer, larger tables) reduces the number of joins required, speeding up query execution.

Simplified Data Model: Denormalized data, such as a star schema (which consists of fact tables and dimension tables), simplifies the structure for end users, making it easier to write queries and create reports in tools like Tableau. A star schema allows queries to retrieve data from a central fact table with minimal joins.

Why Normalize in OLTP:

Data Integrity: In OLTP systems, normalization ensures data consistency by eliminating redundancy. This is crucial for transactional operations where frequent updates and inserts are performed. Each piece of data is stored in one place, making updates more straightforward and reducing the chance of anomalies.

Minimized Storage: Normalization reduces data duplication, which is essential in OLTP to save storage space and maintain a smaller, more manageable database.

**Part5: Perform EDA, Business Insights with Table Data Visulization Tools**

Here are some quick view of our final product:

1. Treemap provides a clear and concise visual summary of which product categories and subcategories contribute most to total sales. Decision-makers can use this insight to focus efforts on top-selling products, identify underperforming categories, or allocate resources based on the sales contribution of each category.
![image](https://github.com/user-attachments/assets/b925387a-88b7-49a3-9a99-454f76cf464d)

2. Map is a powerful tool for visualizing the geographic spread of sales data, revealing where the strongest and weakest sales are located. It helps businesses answer questions like "Where do most of our customers come from?" and "Which regions should we focus on for future growth?" By using color gradients and sales percentages, the map makes it easy to spot patterns and disparities across locations, enabling quick and actionable insights.
![image](https://github.com/user-attachments/assets/5a0699d4-14a6-41a7-8dd7-973327f21057)

3. Bar chart, when animated, can offer powerful insights into how sales performance for different products and categories changes over time. It provides an intuitive way for users to track growth, identify trends, and compare how different product categories perform year after year. The addition of animation enhances the storytelling aspect of the data, helping users see the "big picture" in a dynamic way.
![image](https://github.com/user-attachments/assets/d56a0d57-3b4b-4cb7-bddb-05c6b4cf0c77)


4. The scatter plot is used for representing the relationship between two continuous variables: "Order Quantity" (x-axis) and "Profit" (y-axis). Each point corresponds to a product, with the size of the points representing the total order quantity. The different colors represent clusters created using the K-Nearest Neighbors (KNN) clustering algorithm. This technique groups products with similar order quantities and profits, helping to reveal patterns and similarities in product performance.
![image](https://github.com/user-attachments/assets/0cb30052-b25d-4a8c-8c2f-418a93d57f16)

5. Clustering Insights: 

Cluster 1 (Blue): Consists of products like "Road Bikes" and "Touring Bikes," which generally have low profit margins (negative profits) despite moderate order quantities.
Cluster 2 (Teal): Contains many low- to medium-profit products, with small order quantities but a wider distribution in terms of profit.
Cluster 3 (Orange): Represents medium-profit products with higher order quantities, such as jerseys (Clothes) and helmets (Accessories).
Cluster 4 (Yellow): Contains high-profit products like "Mountain Bikes" and "Mountain Frames," with relatively high profits and moderate order quantities.

Model summary:
![image](https://github.com/user-attachments/assets/fe2a8615-1fd2-433b-a6d4-06945953a862)
![image](https://github.com/user-attachments/assets/4548395e-5117-427e-a690-c9db898875b6)

Clustering Statistics:
1. Number of Clusters: 4 clusters were created.
2. Number of Points: A total of 142 products were used in the analysis.
3. Between-group Sum of Squares: Measures the variability between the clusters (12.686), indicating how distinct the clusters are from one another. A higher value means the clusters are well-separated.
4. Within-group Sum of Squares: Measures the variability within each cluster (5.3942). Lower values indicate that products within the same cluster are more similar.
Total Sum of Squares: The sum of variability across the entire dataset (18.081).

Analysis of Variance (ANOVA):
1. F-statistic: Indicates how well each variable explains the differences between clusters. Higher values mean a variable is more influential in differentiating clusters.
2. Sum of Unit Price: F-statistic of 36.52, indicating it is the most influential variable in differentiating the clusters.
3. Sum of Order Qty: F-statistic of 33.0, also highly significant in separating the clusters.
4. Sum of Freight and Sum of Profit: These have lower F-statistics (30.01 and 15.68, respectively), but still play a role in distinguishing between clusters.
5. p-value: Indicates whether the differences in the variables between clusters are statistically significant. For all variables, the p-value is extremely low (close to 0), suggesting that the differences are highly significant and not due to random variation.

Summary of Insights:
Unit Price and Order Quantity are the most influential variables in separating products into different clusters, as seen by their high F-statistics.
Clusters 1 and 4, which contain fewer products, stand out due to high unit prices but have drastically different profit margins (Cluster 1 has negative profits, while Cluster 4 has positive profits). This suggests that products in Cluster 1 may need attention regarding pricing or cost management.







To to see the whole story, please visit my Tableau Public space!

**Data Source**

[AdventureWorks sample databases](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms)
