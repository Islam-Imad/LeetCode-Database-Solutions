# [Reformat Department Table](https://leetcode.com/problems/reformat-department-table/description/)

```sql
SELECT 
    id,
    SUM(CASE WHEN month = 'Jan' THEN revenue END) AS Jan_Revenue,
    SUM(CASE WHEN month = 'Feb' THEN revenue END) AS Feb_Revenue,
    SUM(CASE WHEN month = 'Mar' THEN revenue END) AS Mar_Revenue,
    SUM(CASE WHEN month = 'Apr' THEN revenue END) AS Apr_Revenue,
    SUM(CASE WHEN month = 'May' THEN revenue END) AS May_Revenue,
    SUM(CASE WHEN month = 'Jun' THEN revenue END) AS Jun_Revenue,
    SUM(CASE WHEN month = 'Jul' THEN revenue END) AS Jul_Revenue,
    SUM(CASE WHEN month = 'Aug' THEN revenue END) AS Aug_Revenue,
    SUM(CASE WHEN month = 'Sep' THEN revenue END) AS Sep_Revenue,
    SUM(CASE WHEN month = 'Oct' THEN revenue END) AS Oct_Revenue,
    SUM(CASE WHEN month = 'Nov' THEN revenue END) AS Nov_Revenue,
    SUM(CASE WHEN month = 'Dec' THEN revenue END) AS Dec_Revenue
FROM Department
GROUP BY id;
```

```sql
SELECT 
    d1.id,
    JAN.Jan_Revenue,
    FEB.Feb_Revenue,
    MAR.Mar_Revenue,
    APR.Apr_Revenue,
    MAY.May_Revenue,
    JUN.Jun_Revenue,
    JUL.Jul_Revenue,
    AUG.Aug_Revenue,
    SEP.Sep_Revenue,
    OCT.Oct_Revenue,
    NOV.Nov_Revenue,
    DDEC.Dec_Revenue
FROM Department d1
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Jan_Revenue
    FROM Department d2
    WHERE d2.month = 'Jan'
) AS JAN ON d1.id = JAN.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Feb_Revenue
    FROM Department d2
    WHERE d2.month = 'Feb'
) AS FEB ON d1.id = FEB.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Mar_Revenue
    FROM Department d2
    WHERE d2.month = 'Mar'
) AS MAR ON d1.id = MAR.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Apr_Revenue
    FROM Department d2
    WHERE d2.month = 'Apr'
) AS APR ON d1.id = APR.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS May_Revenue
    FROM Department d2
    WHERE d2.month = 'May'
) AS MAY ON d1.id = MAY.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Jun_Revenue
    FROM Department d2
    WHERE d2.month = 'Jun'
) AS JUN ON d1.id = JUN.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Jul_Revenue
    FROM Department d2
    WHERE d2.month = 'Jul'
) AS JUL ON d1.id = JUL.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Aug_Revenue
    FROM Department d2
    WHERE d2.month = 'Aug'
) AS AUG ON d1.id = AUG.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Sep_Revenue
    FROM Department d2
    WHERE d2.month = 'Sep'
) AS SEP ON d1.id = SEP.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Oct_Revenue
    FROM Department d2
    WHERE d2.month = 'Oct'
) AS OCT ON d1.id = OCT.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Nov_Revenue
    FROM Department d2
    WHERE d2.month = 'Nov'
) AS NOV ON d1.id = NOV.id
LEFT JOIN (
    SELECT d2.id, d2.revenue AS Dec_Revenue
    FROM Department d2
    WHERE d2.month = 'Dec'
) AS DDEC ON d1.id = DDEC.id
GROUP BY d1.id;
```