# [AdeventureWork_Busssiness_Intelligence_Dashboard] (https://public.tableau.com/app/profile/sung.jen.yen4583/viz/AdventureWorksMarketAnalysis/Story1?publish=yes)

**Motivation**

1. Extract- Perform 3NF normalization by defining the schema and executing CRUD operations for OLTP systems.
2. Transform- Aggregate normalized tables into a star schema to enhance the capability for OLAP operations.
3. Load- Conduct business insight analysis, including clustering analysis for product strategy and cross-tab regional performance evaluation.

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
![image](https://github.com/user-attachments/assets/0836b90c-b9a5-48cc-b0da-271e82d611c3)

...[to see more please visit my Tableau Public space to see the whole story!]

**Data Source**

[AdventureWorks sample databases](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms)
