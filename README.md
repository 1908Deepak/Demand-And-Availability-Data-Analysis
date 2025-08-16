# INSURANCE DATA ANALYSIS

### Dashboard Link :https://app.powerbi.com/groups/9dfd857a-796e-4f06-82d4-c4d57ddb57f0/reports/266d70fb-f7e4-45ac-84ef-e7b3ad6fe072/b1562978409a404112cb?experience=power-bi

## Problem Statement
Businesses often face challenges in balancing customer demand with available supply. Tracking demand and availability across regions, time, and product categories helps improve forecasting, reduce stockouts, and optimize inventory.

## Key Objective

- Analyze total demand vs. availability across locations and time.
- Identify gaps where demand exceeds availability
- Monitor regional trends to improve allocation.
- Provide insights into resource utilization and supply optimization.


### Steps followed 

Step 1 – Data Loading

- Loaded demand dataset from CSV file in into Power BI.

Step 2: Open Power Query Editor and in the View tab under Data Preview, enabled:

- Enabled:

  - Column distribution

  - Column quality

  - Column profile

- Set profiling to "Based on entire dataset".

Also, changed profiling to “Based on entire dataset”.

Step 3 – Data Quality Checks

- No major errors in key fields.
- Some nulls in Demnad, Availability, Product Name


Step 5 : Created KPIs in Report View:
Created card visuals with DAX measures:

      Total Demand = SUM('Demand/Availability'[Demand])

      Total Loss = SUMX(FILTER('Demand/Availability' ,'Demand/Availability'[Loss/profit]<0),'Demand/Availability'[Loss/profit]*'Demand/Availability'[Unit_Price])*-1

      Total Profit = SUMX(FILTER('Demand/Availability' ,'Demand/Availability'[Loss/profit]>0),'Demand/Availability'[Loss/profit]*'Demand/Availability'[Unit_Price])

      Total Supply Shortage = [Total Demand] - [Total Availability]

      Total Days = DISTINCTCOUNT('Demand/Availability'[Order_Date_DD_MM_YYYY])

      Total Availability = SUM('Demand/Availability'[Availability])

      Avg_Loss_Per_Day = DIVIDE([Total Loss] ,[Total Days])

      Avg_Demand = DIVIDE([Total Demand],[Total Days])

      Avg_Availability = DIVIDE([Total Availability] , [Total Days])



Step 8 - Publish to Power BI Service 
- Published dashboard for cloud access and sharing with stakeholders.

![Publish_Message](https://github.com/user-attachments/assets/fefeafa0-4c09-47ac-ad09-2b05ea5d3f8e)

# Dashboard :   Home Page 

![dashboard_snapo](https://github.com/user-attachments/assets/ecf783b2-7178-45e6-97cf-4d42ec99ba15)


 
# Insights

- Regions with persistent demand gaps can be targeted for supply chain improvements.

- Certain product categories consistently show under-supply, requiring reallocation.

- Seasonal patterns reveal spikes in demand not met by available resources.


# Conclusion

This dashboard enables businesses to balance supply and demand effectively. By monitoring demand trends, fulfillment ratios, and regional shortages, organizations can minimize lost sales, optimize resource distribution, and improve customer satisfaction.


## Resources

[Demand Dataset](https://drive.google.com/drive/folders/1C7JxT2EJj1x9_-r28MEKXdaqCdW_ynWC?usp=sharing)


## Authors

- [1908Deepak](https://github.com/1908Deepak)


## Feedback

If you have any feedback, please reach out to us at deepaksingh190810@gmail.com

