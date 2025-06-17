# Nuvora Group. Inc vendor performance Analysis

Tools Used: SQL, python, tableau <br>
Project Type: end-to-end project

## Project Background
Nuvora Group, Inc. is a multi-brand holding company operating across the beverage distribution and retail industry in North America. Since its founding in 2003, Nuvora has grown through strategic acquisitions and partnerships, enabling its subsidiaries to serve thousands of retail and wholesale clients. <br>

The company has gathered comprehensive data on transactions, product categories, vendor performance, purchase behaviors, and profitability metrics of the last year. This project was developed in collaboration with the business strategy and procurement teams to clean, analyze, and visualize the data using SQL, Python, and Tableau.  <br>

Insights and recommendations are provided on the following key areas:
- Brand Performance: Identify underperforming brands that require promotional or pricing adjustments.
- Sales: Determine top vendors contributing to sales and gross profit.
- Purchasing Strategy: Analyze the impact of bulk purchasing on unit costs.
- Inventory Management: Assess inventory turnover to reduce holding costs and improve efficiency.
- Profitability Analysis: Investigate the profitability variance between high-performing and low-performing vendors.

## Relevant Resources
- The raw dataset used for analysis can be accessed [here](https://drive.google.com/drive/folders/135tgUOCXse7rB9N2nH6Rwpfv3wus63-_?usp=drive_link). <br>
- The SQL script for data extraction and visualization is available [here](https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/ingestion_db.py). <br>
- The SQL script for data cleaning is available [here](https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/get_vendor_summary.py). <br>
- The Python script used for data analysis can be accessed [here](https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/Vendor_performance_analysis.ipynb). <br>
- The final cleaned dataset used for analysis can be accessed [here](https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/vendor_sales_summary.csv). <br>
- The final Tableau dashboard can be viewed [here](https://public.tableau.com/views/dashboard_17501638543320/Dashboard1?:language=es-ES&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link). <br>
- A presentation slide deck prepared for stakeholders can be viewed here. <br>

## Data structure and initial checks
The Nuvora Group, Inc. dataset consists of six structured tables: Sales, Begin Inventory, End Inventory, Purchase Prices, Purchases, and Vendor Invoice with over 15 million records combined. <br>

Prior to beginning the analysis, a variety of checks were conducted for quality control and to gain familiarity with the data structure. These included schema validation, relationship consistency, data type integrity, and record count verification. Once validated, the workflow followed a structured process: raw data was explored and cleaned using SQL, merging the datasets into an aggregated performance table. This table was saved into a database and loaded into Python for deeper analysis, including exploratory data analysis, and answering stakeholder-driven questions. The findings were then visualized through a Tableau dashboard, and summarized in a final report to guide business decisions. <br>

To align the analysis with business needs, a set of stakeholder-oriented questions was outlined. These informed the creation of calculated fields, aggregations, and filters used in the dashboard.

## Executive summary
Nuvora Group, Inc. conducted a year-long (2024) analysis of vendor and brand performance across its retail network. Top 10 vendors contributed 65.69% of purchases, raising concentration risks. Diageo led in volume, while 198 brands showed high margins but low sales. Bulk buying cut unit costs by 72%, and $2.71M in unsold inventory highlighted cash flow inefficiencies. Statistical tests confirmed margin differences between vendor groups. Profitability was found to depend more on pricing and volume strategy than on unit cost or turnover. Key opportunities for growth and optimization are outlined in the sections that follow. <br> 

Below is the overview page of the dashboard, and the full  version can be viewed [here](https://public.tableau.com/views/dashboard_17501638543320/Dashboard1?:language=es-ES&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link). <br>

![Dashboard Preview](https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/Dasboard.png)

## Insights Deep-Dive 
### Brand Performance
- 198 brands show high margins but low sales, indicating missed revenue opportunities. These are strong candidates for marketing, bundling, or pricing strategies to boost volume without hurting profitability.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/brandslowsaleshighprofit.png" alt="Preview" />
</p>

### Sales & Vendor Contribution
- The top 10 vendors account for 65.69% of purchases, revealing potential over-reliance. This concentration poses supply chain and pricing risks, making vendor diversification a recommended strategy.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/donut.png" alt="Preview" />
</p>

- The Pareto chart shows that Diageo North America Inc leads with 16.3% of purchases, and the top 10 vendors collectively contribute 65.69%. Most remaining vendors contribute under 5% each, forming a long tail with limited individual impact.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/pareto.png" alt="Preview" />
</p>

### Purchasing Strategy
- Vendors placing large orders paid 72% less per unit on average ($10.78 vs. $39.07), highlighting the cost-efficiency of bulk purchasing and supporting volume-based procurement strategies to optimize margins.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/bulksize.png" alt="Preview" />
</p>

- Unsold inventory amounts to $2.71M, with Diageo North America Inc responsible for $722K. Reducing this stagnant stock can lower storage costs and enhance cash flow and profitability.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/unsoldinventory.png" alt="Preview" />
</p>

- Stock turnover ranged from 0 to 274.5, with several vendors below 1.0, indicating slow-moving or excess inventory. Turnover above 1 may reflect sell-through of older stock, potentially hiding stock management inefficiencies.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/stockturnover.png" alt="Preview" />
</p>


### Profitability Analysis
- Top vendors average a 31.17% profit margin, while low-performing vendors reach 41.55%. The histogram confirms this difference is statistically significant, suggesting that higher margins among low performers may reflect pricing or visibility issues limiting sales.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/histogram.png" alt="Preview" />
</p>

- Correlation analysis showed strong alignment between purchases and sales, but weak links between profitability and factors like purchase price or stock turnover. This suggests that profitability depends more on pricing strategy, volume mix, and cost control than on unit cost or inventory speed alone.

<p align="center">
  <img src="https://github.com/DanielaRubianoB/nuvora-vendor-performance-analysis/blob/main/images/correlation.png" alt="Preview" />
</p>

### Statistical Analysis
- Statistical testing (p-value from t-test) confirmed a significant difference in profit margins, indicating that high-margin and high-volume vendors follow distinct profitability models.
- Purchase price showed a weak negative correlation with both sales and profit (–0.012, –0.016), suggesting unit cost alone doesn’t drive profitability and highlighting the need for broader pricing strategy reviews.
- Total purchase quantity and total sales quantity show a strong correlation (0.999), confirming efficient inventory turnover and indicating that backend processes are working well for most SKUs.
- Profit margin and total sales price show a negative correlation (–0.179), suggesting that raising prices may reduce margins due to lower volume, emphasizing the need to balance pricing with demand.
- Stock turnover shows a weak negative correlation with profitability (–0.038, –0.055), indicating that faster inventory movement doesn’t guarantee better margins and highlighting the need to prioritize margin optimization.


## Recommendations & Opportunities
- Re-evaluate pricing for low-sales, high-margin brands: Identify and adjust pricing strategies for 198 brands with strong profit margins but low sales volume to boost revenue without compromising profitability.
- Diversify vendor partnerships: Reduce dependency on top vendors (currently contributing 65.69% of total purchases) by onboarding alternative suppliers to improve supply chain resilience and mitigate risk.
- Leverage bulk purchasing efficiency: Utilize bulk order strategies that lower unit purchase prices by up to 72%, particularly for high-demand or consistently sold products to optimize cost structures.
- Optimize slow-moving inventory: Reassess purchase quantities, initiate clearance sales, or repurpose stagnant stock to recover capital tied up in over $2.71M of unsold inventory.
- Improve vendor evaluation metrics: Move beyond sales volume by integrating profit margin and inventory turnover into vendor assessments. Prioritize support for high-margin vendors struggling with sales volume.
- Streamline product portfolio: Eliminate persistently low-performing products and reallocate resources toward SKUs with stronger margin-to-sales efficiency.
- Align promotional strategies with data insights: Use dashboard results to identify high-potential products and vendors for future campaigns, ensuring marketing efforts align with profitability drivers.
- Enhance inventory planning with data-driven monitoring: Extend reporting tools to continuously track KPIs like stock turnover, gross profit, and margin variance across vendors and categories.

## Key Questions for Stakeholders Prior to Project Advancement
These are some questions I asked stakeholders/project leads early on to better understand business goals, clarify assumptions, and ensure data interpretation aligned with operational context:
- Some products report negative gross profit and margins. Are these pricing errors, returns, or edge cases such as promotional loss leaders?
- Freight cost ranges from $0.09 to over $250,000. Should extremely high values be considered valid bulk shipments or flagged for possible entry errors?
- Unit prices range from under $1 to over $7,000. Are these valid premium items or signs of misclassification or currency entry mistakes?
- Stock turnover values exceed 250 for some items. Are these true fast-movers, system-generated anomalies, or the result of historical inventory adjustments?
- Should we apply manual overrides or business rules to clean outliers, or retain them to reflect raw operational data?
- Is this dashboard meant for one-time strategic use, or will it support ongoing performance tracking and reporting?


## Assumptions and Caveats
The following assumptions and limitations were made during the course of this project due to gaps in context, incomplete metadata, or missing documentation:
- Data was filtered to exclude entries with gross profit ≤ 0, profit margin ≤ 0, and sales quantity = 0, assuming these reflect errors or exceptions, and to focus the analysis on active, profitable transactions.
- All prices and costs were assumed accurate despite some extreme outliers, which were included in the analysis unless clearly erroneous.
- Turnover values above 1 were interpreted as sell-through from existing stock, indicating inventory movement even without current-year purchases.
- Vendor-brand relationships were assumed to remain static throughout the analysis period; changes in ownership or supply chains were not accounted for.
- Unit prices were assumed to be static, as the analysis did not account for discounts or pricing changes over time due to missing timestamped pricing data.
- Profit margin calculations assume consistent cost attribution; variability in indirect costs, freight, or discounts may cause margin distortion not reflected in this analysis.
