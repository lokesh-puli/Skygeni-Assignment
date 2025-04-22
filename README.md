# Skygeni-Assignment
This repository contains code and resources for solving my assignment questions for the role of Data Engineer at Skygeni. It consists of four datasets and four questions related to Data Analytics. I have shown the results in screenshots as well. This project focuses on analyzing customer subscription patterns and payments using four interconnected datasets.

---

## Datasets Used

1. **Subscription Information Dataset**
   Columns: `client_id`, `subscription_type`,	`start_date`,	`end_date`,	`renewed`
2. **Industry Client Details Dataset**
   Columns: `client_id`,	`company_size`,	`industry`,	`location`
3. **Payment Information Dataset**
   Columns: `client_id`,	`payment_date`,	`amount_paid`,	`payment_method`
4. **Financial Information Dataset**
   Columns: `start_date`,	`end_date`,	`inflation_rate`, `gdp_growth_rate`

   ---

## Assignment Questions & Approach
   
### 1. How many Finance Lending andd Blockchain clinets does the organization have?
  - Used the **Industry Client Details Dataset**
  - Filtered records where `industry` is `"Finance Lending"` or `"Blockchain"`
  - Counted the number of unique `client_id`s per industry using `"Value_counts()"`
  - Visualized with a count plot to show the count of clients of the industries 
  - **Output reflects:** 22 Clients in Finance Lending and 25 clients in Blockchain industries
  
      ---
 ### 2. Which industry in the organization has the highest renewal rate?
  - Merged the **Subscription Information Dataset** and **Industry Client Details Dataset**  on `client_id`
  - Grouped by 'industry' and calculated the mean of the `renewed` columns
  - Boolean values were treated as integers (`True=1`, `False=0`), so `.mean()` represents the renewal rate
  - Identified the industry with the highest rate using `.idxmax()`
  - Visualized with a bar chart to compare all industries
  - **Output reflects:** Gaming is the industry with highest renwal rate

    ---
  ### 3. What was the average inflation rate when their subscriptions were renwed?
   - Extracted the `year` from `subscription_date` in the **Subscription Information Dataset** 
   - Merged with the **Financial Information Dataset** on the column `year`
   - Filtered records where `renewed == True`
   - Calculated the mean of the `inflation_rate` for those renewed subscriptions
   - **Output reflects:** the average inflation rate is 4.311 when their subscriptions are renewed

     ---
  ### 4. Whatis the median amount paid each year for all the payment methods?
   - Extracted the `year` from the `payment_date` in the **Payment Information Dataset**
   - Grouped by both `year`, then calculated the median of `amount_paid'
   - **Output reflects:** the median of all payment methods in each year.
   -  Grouped by both `year` and `payment_method`, then calculated the median of `amount_paid'
   -  **Output reflects:** the median of all payment methods separately in each year.
   -  Renamed the column to `median_amount_paid` for clarity

      ---
  ## Tools & Technologies:
   - **Python**
   - **Libraries:** `Pandas`, `Numpy`, `Seaborn`, `Matplotlib`
   - **Jupyter Notebook** for analysis and visualization

  ## Contact
   lokeshpuli472@gmail.com <br>
   - Lokesh Puli
    
    
    
