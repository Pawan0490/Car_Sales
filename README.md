


# Car Sales  

### Report Link :https://drive.google.com/file/d/1jHEPaa43Q9wQTxEQ_zFX7xxe6Rysc7aw/view?usp=drive_link 

Objective: The objective of this project is to design and develop a dynamic and interactive Car Sales Dashboard using Power BI. The dashboard will visualize critical KPIs related to our car sales, helping us understand our sales performance over time and make data-driven decisions.


### Steps followed 
 Data ETL and Visualization Steps:

    1. Data Cleaning and Preparation: Removed duplicate entries, handled missing values using imputation and Standardized data formatting.

    2. Data Loading: The Excel dataset was loaded into Power BI Desktop, selecting the data transformation mode before uploading.

    3. Theme Selection: A theme was selected in the report view under the "View" tab.

    4. Key Metric Display: Card visuals were used to display key numerical values, including the number of YTD total sales, YOY growth in total sales, YTD average, and MTD Cars sold etc.

    5. Categorical Data Visualization : Donut charts were used to visualize categorical data related to car sales by colour and car sales by body style.

    6. Bar Graph Usage (Demographic and Location Data): Bar graphs were used to display YTD car slod by dealar region. 

    7. Area Chart is used to show YTD weekly sales trend 

    8. A separate report sheet includes a table chart designed to highlight the major columns and provide a summary of their respective total sales.



To prepare this report, Power BI's built-in functions were utilized, which facilitated the data modification, binning and cleaning. Additionally, various DAX formulas were applied to create a separate Measure table containing over 25 calculated measures. Some of these are shown below.


* A new measure was created to provide a sales overview: Year-to-Date (YTD) Total Sales, Month-to-Date (MTD) Total Sales, Year-over-Year (YOY) Growth in Total Sales, and the difference between YTD Sales and Previous Year-to-Date (PTYD) Sales.

Following DAX expression were written:
        
        YTD Total Sales = TOTALYTD(sum(car_data[Price ($)]),'Calander Table'[Date])
        MTD Total Sales = TOTALMTD(sum(car_data[Price ($)]), 'Calander Table'[Date])
        YOY growth = [Sales Difference]/[PYTD Total Sales]
        Sales Difference = [YTD Sales]-[PYTD Total Sales]
        Sales Diff Color = if([Sales Difference]>0, "Green", "Red")

Similar DAX formulas were used to calculate the Average Price Analysis and Cars Sold metrics
        
A card visual was used to represent Sales Overview, Average Price Analysis and Cars Sold metrics

![Image](https://github.com/user-attachments/assets/98e85eb7-fac2-4878-8bd2-c2f147ff36b0)

        
 * A new measure was created to highlight the maximum point for the YTD weekly sales trend
 
 Following DAX expression was written
 
         Max Point = IF([Total Sales] = MAXX(ALLSELECTED('Calander Table'[Week]), [Total Sales]), [Total Sales], BLANK())
 
* An area chart visual was used to represent the maximum selling week
 
 Snap of YTD weekly sales trend
 
 ![Image](https://github.com/user-attachments/assets/f67665ae-7303-4021-bb70-d1194243437b)
 
*  To show region-wise car sales, the YTD car sales measure was used.
 
 Following DAX expression was written
 
        YTD Car Sold = TOTALYTD(COUNT(car_data[Car_id]), 'Calander Table'[Date])
    
 A Bar graph visual was used to represent this region wise sales.
 
 
 ![Image](https://github.com/user-attachments/assets/d32cc383-419c-4540-b6fd-d55910d473bc)
 
* Categorical data regarding car sales, segmented by color and body style, was presented through donut charts
 

 ![Image](https://github.com/user-attachments/assets/eaebe2d2-6e0a-40e6-8abd-c091b1db9245)

 * Company-wise sales trends were showcased in tabular form, emphasizing YTD sales and the YTD sales growth percentage 

Following DAX expression was written

     YTD Sales = TOTALYTD(sum(car_data[Price ($)]),'Calander Table'[Date])
     YTD Car Sold = TOTALYTD(COUNT(car_data[Car_id]), 'Calander Table'[Date])
     YTD Avg Price = TOTALYTD([Avg Price], 'Calander Table'[Date])

* A detailed grid was created to display all relevant car sale information, including model, body style, color, sales amount, dealer region, and date


![Image](https://github.com/user-attachments/assets/aeaacd12-f873-4266-836e-37ae504a15bc)

# Snapshot of Dashboard (Power BI Service)

![Image](https://github.com/user-attachments/assets/3290d4da-a8b6-492f-b201-5a5c6dfd6ddc)
 

 # Report Snapshot (Power BI DESKTOP)

 
![Image](https://github.com/user-attachments/assets/5a034ab1-51a1-4d0d-b683-8378a69ffd89)

# Insights

A two pages report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Sales Insight 

 a) YTD (Year to Date) total sales- $371.2M

 b) MTD (Month to Date) total sales- $54.28M

 c) Sales difference (YTD-PYTD)- $71M

 e) Year-over-Year (YOY) Growth in Total Sales- 23.6%

 f) YTD average price- $20K

 g) MTD average price- $28.2K

 h) Average price difference from privious year- -$0.22K

 i) YOY Growth in Average Price- -0.8%

 j) YTD car sold- 13K

 k) MTD car sold- $20K

 l) Difference between YTD Cars Sold and PTYD Cars Sold- $2.6K

 m) YOY Growth in Cars Sold- $24.6%
 

    Despite a slight decrease in average price compared to last year, YTD sales surged to $371.2M, driven by a 24.6% increase in cars sold, indicating strong overall growth with a 23.6% YOY sales increase
           
### [2] YTD Sales Insight

 a) Week 36 exhibited the maximum sales volume of $15M, whereas week 53 experienced the minimum sales volume of $1M

 b) YTD car sales body wasie : 

     1) SUV- 27%
     2) Hatchback- 22%
     3) Sidan-20%
     4) Passanger - 17%
     5) Hardtop- 14%

c) YTD car sales by colour:

     1) Pale white- 40%
     2) Black- 40%
     3) Red- 20%

d) Top 5 YTD car sales by dealar region:

     1) Austin- 2.3K
     2) Janesville- 2.1K
     3) Scottsdale- 1.9K
     4) Pasco- 1.7K
     5)Greenville- 1.7K
  
    Thus, YTD sales peaked at $15M in week 36 and bottomed at $1M in week 53, with SUV and Hatchback body styles dominating sales alongside Pale White and Black colors, and Austin leading dealer region sales


  ### [3] Compny wise sales trend

 a) Chevrolet- 7.30%

 b) Ford- 6.85%

 c) Dodge- 6.74% 

 d) Jaguar- 0.67%

 e) Hyundai- 0.69%

    Thus, Chevrolet leads car sales at 7.30%, followed closely by Ford and Dodge, while Jaguar and Hyundai represent the smallest market shares, each under 1%


### In conclusion, despite a marginal dip in average vehicle price, the year witnessed robust sales growth, culminating in $371.2M in YTD sales, fueled by a significant increase in units sold. Peak sales occurred in week 36, showcasing the strength of SUV and Hatchback models, particularly in popular colors like Pale White and Black, and the dominant performance of the Austin dealer region. While Chevrolet maintained its leading market share, followed by Ford and Dodge, niche brands like Jaguar and Hyundai represented smaller segments. Overall, the data indicates a strong market with notable growth driven by volume, despite slight pricing variations


Source- https://drive.google.com/drive/folders/1h6RQTGkoMOqovVUh9qf_nX5bI1_Meg8w

