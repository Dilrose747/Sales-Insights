# 1.TOTAL SALES BY REGION
SELECT Region, SUM(Sales) AS TotalSales
FROM Orders
GROUP BY Region
ORDER BY TotalSales DESC;

# Region, TotalSales
'West\r', '725514.00'
'East\r', '678834.00'
'Central\r', '501256.00'
'South\r', '391750.00'

The West region is the top contributor to sales. Marketing campaigns and supply chain investments can be focused here to maximize revenue

# 2. PROFIT BY PRODUCT CATEGORY
SELECT P.Category, SUM(O.Profit) AS TotalProfit
FROM Orders O
JOIN Products P ON O.ProductID = P.ProductID
GROUP BY P.Category
ORDER BY TotalProfit DESC;

# Category, TotalProfit
'Technology', '875140.00'
'Office Supplies', '855332.00'
'Furniture', '171897.00'

Technology is the most profitable category. Prioritize stock and promotions in this segment.

# 3. MONTHLY SALES TREND
SELECT DATE_FORMAT(OrderDate, '%Y-%m') AS Month, SUM(Sales) AS TotalSales
FROM Orders
GROUP BY DATE_FORMAT(OrderDate, '%Y-%m')
ORDER BY Month;

# Month, TotalSales
'2014-01', '28959.00'
'2014-02', '12740.00'
'2014-03', '54796.00'
'2014-04', '24710.00'
'2014-05', '29640.00'
'2014-06', '29289.00'
'2014-07', '35348.00'
'2014-08', '37858.00'
'2014-09', '66113.00'
'2014-10', '34561.00'
'2014-11', '64816.00'
'2014-12', '65425.00'
'2015-01', '29351.00'
'2015-02', '20728.00'
'2015-03', '40881.00'
'2015-04', '38054.00'
'2015-05', '30934.00'
'2015-06', '28865.00'
'2015-07', '28732.00'
'2015-08', '50095.00'
'2015-09', '66734.00'
'2015-10', '32028.00'
'2015-11', '50738.00'
'2015-12', '53420.00'
'2016-01', '38056.00'
'2016-02', '49240.00'
'2016-03', '49614.00'
'2016-04', '45196.00'
'2016-05', '64967.00'
'2016-06', '38998.00'
'2016-07', '42778.00'
'2016-08', '46347.00'
'2016-09', '41989.00'
'2016-10', '52277.00'
'2016-11', '66839.00'
'2016-12', '72954.00'
'2017-01', '64740.00'
'2017-02', '50024.00'
'2017-03', '74779.00'
'2017-04', '39074.00'
'2017-05', '40884.00'
'2017-06', '47738.00'
'2017-07', '54392.00'
'2017-08', '75684.00'
'2017-09', '74175.00'
'2017-10', '65509.00'
'2017-11', '89313.00'
'2017-12', '56972.00'

Sales show seasonal peaks in Q4, suggesting strong holiday demand. Inventory planning should account for this.

# 4. TOP 10 CUSTOMERS BY TOTAL SALES
SELECT C.CustomerName, SUM(O.Sales) AS TotalSales
FROM Orders O
JOIN Customers C ON O.CustomerID = C.CustomerID
GROUP BY CustomerName
ORDER BY TotalSales DESC
LIMIT 10;

# CustomerName, TotalSales
'Ken Lonsdale', '411075.00'
'Sean Miller', '375630.00'
'Seth Vernon', '367104.00'
'Greg Tran', '342809.00'
'John Lee', '333166.00'
'Edward Hooks', '330016.00'
'Sanjit Chand', '311190.00'
'Clay Ludtke', '304668.00'
'Adrian Barton', '289520.00'
'Raymond Buch', '272106.00'

Top 10 customers contribute disproportionately to sales. Consider loyalty programs or account-based marketing for these clients.

# 5. AVERAGE DISCOUNT BY REGION
SELECT Region, AVG(Discount) AS AvgDiscount
FROM Orders
GROUP BY Region;

# Region, AvgDiscount
'South\r', '0.147253'
'West\r', '0.109335'
'Central\r', '0.240353'
'East\r', '0.145365'

Discount rates are relatively uniform, but slightly higher in the Central Region. Review pricing strategy for consistency.

# 6. PROFIT BY CATEGORY AND SUB-CATEGORY
SELECT P.Category, P.Subcategory, ROUND(SUM(O.Profit), 2) AS TotalProfit
FROM Orders O
JOIN Products P ON O.ProductID = P.ProductID
GROUP BY P.Category, P.Subcategory
ORDER BY TotalProfit DESC;

# Category, Subcategory, TotalProfit
'Technology', 'Accessories\r', '329553.00'
'Technology', 'Copiers\r', '295342.00'
'Technology', 'Phones\r', '255704.00'
'Office Supplies', 'Binders\r', '243073.00'
'Office Supplies', 'Paper\r', '228868.00'
'Furniture', 'Chairs\r', '206146.00'
'Office Supplies', 'Storage\r', '170035.00'
'Office Supplies', 'Appliances\r', '98606.00'
'Furniture', 'Furnishings\r', '82855.00'
'Office Supplies', 'Labels\r', '39347.00'
'Office Supplies', 'Art\r', '38026.00'
'Office Supplies', 'Envelopes\r', '37028.00'
'Office Supplies', 'Fasteners\r', '6320.00'
'Technology', 'Machines\r', '-5459.00'
'Office Supplies', 'Supplies\r', '-5971.00'
'Furniture', 'Bookcases\r', '-16302.00'
'Furniture', 'Tables\r', '-100802.00'

Technology is the most profitable category and Accessories are the top-profit subcategories. Promotions and stock levels should prioritize these.

# 7. MONTHLY PROFIT TREND
SELECT DATE_FORMAT(OrderDate, '%Y-%m') AS Month, ROUND(SUM(Profit), 2) AS TotalProfit
FROM Orders
GROUP BY Month
ORDER BY Month;

# Month, TotalProfit
'2014-01', '4549.00'
'2014-02', '2650.00'
'2014-03', '91.00'
'2014-04', '4603.00'
'2014-05', '3912.00'
'2014-06', '4499.00'
'2014-07', '-1782.00'
'2014-08', '2079.00'
'2014-09', '10221.00'
'2014-10', '4070.00'
'2014-11', '6649.00'
'2014-12', '7979.00'
'2015-01', '1238.00'
'2015-02', '2172.00'
'2015-03', '9172.00'
'2015-04', '6132.00'
'2015-05', '2781.00'
'2015-06', '4782.00'
'2015-07', '668.00'
'2015-08', '10111.00'
'2015-09', '9927.00'
'2015-10', '3430.00'
'2015-11', '5580.00'
'2015-12', '5613.00'
'2016-01', '8499.00'
'2016-02', '14686.00'
'2016-03', '1951.00'
'2016-04', '7426.00'
'2016-05', '9970.00'
'2016-06', '4481.00'
'2016-07', '6122.00'
'2016-08', '863.00'
'2016-09', '5169.00'
'2016-10', '8250.00'
'2016-11', '3054.00'
'2016-12', '11319.00'
'2017-01', '10873.00'
'2017-02', '4238.00'
'2017-03', '18130.00'
'2017-04', '-5886.00'
'2017-05', '7570.00'
'2017-06', '7400.00'
'2017-07', '4998.00'
'2017-08', '11760.00'
'2017-09', '9219.00'
'2017-10', '6573.00'
'2017-11', '11142.00'
'2017-12', '7414.00'

Profit also peaks in Q4, aligned with sales trends. Price optimization can maximize Q4 profitability.

# 8. DISCOUNT IMPACT ON PROFIT
SELECT ROUND(Discount, 2) AS DiscountRate, ROUND(SUM(Profit), 2) AS TotalProfit, COUNT(*) AS OrderCount
FROM Orders
GROUP BY DiscountRate
ORDER BY DiscountRate;

# DiscountRate, TotalProfit, OrderCount
'0.00', '320946.00', '4798'
'0.10', '9025.00', '94'
'0.15', '1416.00', '52'
'0.20', '90344.00', '3657'
'0.30', '-10362.00', '227'
'0.32', '-2390.00', '27'
'0.40', '-23052.00', '206'
'0.45', '-2493.00', '11'
'0.50', '-20508.00', '66'
'0.60', '-5944.00', '138'
'0.70', '-40089.00', '418'
'0.80', '-30546.00', '300'

High discounts (>20%) result in negative profit. Review discounting strategy to avoid margin erosion.

# 9. SALES AND PROFIT BY CUSTOMER SEGMENT AND REGION
SELECT C.Segment, O.Region, ROUND(SUM(O.Sales), 2) AS TotalSales, ROUND(SUM(O.Profit), 2) AS TotalProfit
FROM Orders O
JOIN Customers C ON O.CustomerID = C.CustomerID
GROUP BY C.Segment, O.Region
ORDER BY TotalSales DESC;

# Segment, Region, TotalSales, TotalProfit
'Consumer', 'West\r', '5883665.00', '904388.00'
'Consumer', 'East\r', '5643333.00', '725481.00'
'Consumer', 'Central\r', '4139692.00', '116999.00'
'Corporate', 'West\r', '3437912.00', '541947.00'
'Corporate', 'East\r', '3188835.00', '382841.00'
'Consumer', 'South\r', '3015413.00', '404745.00'
'Corporate', 'Central\r', '2462176.00', '293260.00'
'Home Office', 'West\r', '1935602.00', '242745.00'
'Home Office', 'East\r', '1830328.00', '380349.00'
'Corporate', 'South\r', '1770495.00', '271096.00'
'Home Office', 'Central\r', '1394346.00', '197835.00'
'Home Office', 'South\r', '1216202.00', '85925.00'

Consumer segment in the West is highly profitable. Sales teams should target this segment/region combination.

# 10. AVERAGE ORDER VALUE BY CUSTOMER SEGMENT
SELECT C.Segment, ROUND(SUM(O.Sales) / COUNT(DISTINCT O.OrderID), 2) AS AvgOrderValue
FROM Orders O
JOIN Customers C ON O.CustomerID = C.CustomerID
GROUP BY C.Segment
ORDER BY AvgOrderValue DESC;

# Segment, AvgOrderValue
'Consumer', '7224.32'
'Corporate', '7172.67'
'Home Office', '7014.83'

Consumer segment has the highest average order value. Prioritize retention and upselling for this segment.

# 11. BEST SELLING PRODUCTS
SELECT P.ProductName, ROUND(SUM(O.Sales), 2) AS TotalSales, SUM(O.Quantity) AS TotalUnitsSold
FROM Orders O
JOIN Products P ON O.ProductID = P.ProductID
GROUP BY P.ProductName
ORDER BY TotalSales DESC
LIMIT 10;

# ProductName, TotalSales, TotalUnitsSold
'Canon imageCLASS 2200 Advanced Copier', '308000.00', '100'
'Fellowes PB500 Electric Punch Plastic Comb Binding Machine with Manual Bind', '274540.00', '310'
'GBC DocuBind TL300 Electric Binding System', '218064.00', '407'
'HON 5400 Series Task Chairs for Big and Tall', '174960.00', '312'
'GBC Ibimaster 500 Manual ProClick Binding System', '171234.00', '432'
'Bretford Rectangular Conference Table Tops', '155964.00', '552'
'Hewlett Packard LaserJet 3310 Copier', '150720.00', '304'
'SAFCO Arco Folding Chair', '150475.00', '689'
'Hon Deluxe Fabric Upholstered Stacking Chairs, Rounded Back', '127656.00', '612'
'Tennsco 6- and 18-Compartment Lockers', '120175.00', '473'

Focus on top-selling products for inventory planning and promotions.

# 12. ORDERS THAT ARE NOT PROFITABLE
SELECT O.OrderID, O.ProductID, O.Quantity, O.Sales, O.Discount, O.Profit
FROM Orders O
WHERE O.Profit < 0
ORDER BY O.Profit ASC;

# OrderID, ProductID, Quantity, Sales, Discount, Profit
'CA-2016-108196', 'TEC-MA-10000418', '5', '4500.00', '0.70', '-6600.00'
'US-2017-168116', 'TEC-MA-10004125', '4', '8000.00', '0.50', '-3840.00'
'CA-2014-169019', 'OFF-BI-10004995', '8', '2178.00', '0.80', '-3702.00'
'CA-2017-134845', 'TEC-MA-10000822', '5', '2550.00', '0.70', '-3400.00'
'US-2017-122714', 'OFF-BI-10001120', '5', '1890.00', '0.80', '-2929.00'
'CA-2015-147830', 'TEC-MA-10000418', '2', '1800.00', '0.70', '-2640.00'
'CA-2017-131254', 'OFF-BI-10003527', '6', '1525.00', '0.80', '-2288.00'
'CA-2015-116638', 'FUR-TA-10000198', '13', '4298.00', '0.40', '-1862.00'
'CA-2016-130946', 'OFF-BI-10004995', '4', '1089.00', '0.80', '-1851.00'
'CA-2014-145317', 'TEC-MA-10002412', '6', '22638.00', '0.50', '-1811.00'
'US-2015-150630', 'FUR-BO-10004834', '7', '3083.00', '0.50', '-1665.00'
'CA-2014-165309', 'OFF-BI-10001359', '5', '897.00', '0.80', '-1480.00'
'CA-2014-139892', 'TEC-MA-10000822', '8', '8160.00', '0.40', '-1360.00'
'US-2017-120390', 'OFF-BI-10004995', '4', '1633.00', '0.70', '-1307.00'

Non-profitable orders often have high discounts. Pricing controls needed.

# 13. CUSTOMER LIFETIME VALUE (CLV)
SELECT C.CustomerID, C.CustomerName, ROUND(SUM(O.Sales), 2) AS CustomerLifetimeValue
FROM Orders O
JOIN Customers C ON O.CustomerID = C.CustomerID
GROUP BY C.CustomerID, C.CustomerName
ORDER BY CustomerLifetimeValue DESC;

# CustomerID, CustomerName, CustomerLifetimeValue
'KL-16645', 'Ken Lonsdale', '411075.00'
'SM-20320', 'Sean Miller', '375630.00'
'SV-20365', 'Seth Vernon', '367104.00'
'GT-14710', 'Greg Tran', '342809.00'
'JL-15835', 'John Lee', '333166.00'
'EH-13765', 'Edward Hooks', '330016.00'
'SC-20095', 'Sanjit Chand', '311190.00'
'CL-12565', 'Clay Ludtke', '304668.00'
'AB-10105', 'Adrian Barton', '289520.00'
'RB-19360', 'Raymond Buch', '272106.00'
'ZC-21910', 'Zuschuss Carroll', '248868.00'
'PP-18955', 'Paul Prost', '246636.00'
'JD-15895', 'Jonathan Doherty', '243488.00'
'ME-17320', 'Maria Etezadi', '234630.00'
'SE-20110', 'Sanjit Engle', '231971.00'
'KD-16495', 'Keith Dawkins', '229152.00'
'TC-20980', 'Tamara Chand', '228600.00'

High CLV customers should receive personalized offers to maintain loyalty.

# 14. YEARLY SALES AND PROFIT TREND
SELECT YEAR(OrderDate) AS Year, ROUND(SUM(Sales), 2) AS TotalSales, ROUND(SUM(Profit), 2) AS TotalProfit
FROM Orders
GROUP BY Year
ORDER BY Year;

# Year, TotalSales, TotalProfit
'2014', '484255.00', '49520.00'
'2015', '470560.00', '61606.00'
'2016', '609255.00', '81790.00'
'2017', '733284.00', '93431.00'

Sales and profit are growing year over year. Strategy can focus on sustaining this trend.

# AUTHOR
MOHAMED DILROSE P M






