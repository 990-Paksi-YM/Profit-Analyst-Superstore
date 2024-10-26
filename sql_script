-- "Profit Analyst"
-- For Who: Management
-- % contributin againts total profit by category Product (Show SUM TOTAL of Profit)
-- % contributin againts total profit by region (Show SUM TOTAL of Profit)
-- % contributin againts total profit by Segment (Show SUM TOTAL of Profit)
-- Trend Profit by Quartyl     
-- Trend Profit by Year-on-Year (Also show %Year-on-Year Growth)
-- Comparassion profit between quartal year now and last quartal year (use bar chart)
-- Data Need: Order_ID, Sales, Profit, Category, Order_Date, Segment, Region, Contribution profit againts sum of total profit
-- Calculation : Numerator (profit by Order_ID) / Denominator (sum total profit)

WITH D AS (
  SELECT
    SUM(Profit) AS sumtotalprofit
  FROM
    `dqlab-yudha-sample1.dqlab.SuperStores`
),

N AS (
  SELECT
    Order_ID,
    profit,
    Category,
    Order_Date,
    Segment,
    Region
  FROM
    `dqlab-yudha-sample1.dqlab.SuperStores`
)

SELECT
  N.Order_ID,
  SUM(N.Profit) AS Profit_New,
  N.Category,
  N.Order_Date,
  N.Segment,
  N.Region,
  SUM((N.Profit) / D. sumtotalprofit) AS ContributionProfit
FROM
  D,
  N
GROUP BY
  N.Order_ID,
  N.Category,
  N.Order_Date,
  N.Segment,
  N.Region
;
