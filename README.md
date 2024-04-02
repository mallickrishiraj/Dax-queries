# Dax-queries
Performing some basic dax queries

## To find the total number of orders we can use the COUNT formula
1. Create a new measure
2. Rename the measure according to your choice.
3.TotalNumberOfOrders = COUNT(Orders[Order ID])
4. Use the COUNT function to find the number of orders using order ID
5. There is another way to this by counting the rows by using CountRows = COUNTROWS(Orders)
6. To find the unique rows you can use UniqueCount = DISTINCTCOUNT(Orders[Order ID])
7. In order to find the sum of orders made you can use SumOfOrders = SUM(Orders[Quantity])
8. You can add the name field under columns to find the name of the customers who made the highest purchase.

## Performing quick measure feature.
1. Using the quick perform function lets find out the Profit cost
2. First we need to select the type of calculation from the drop down menu.
3. We select the subtraction option
4. Then we add the base value and the value to subtract i.e selling price and product cost respectively.
5. Then click on add.

## Calculating the total profit 
1. We can calculate the total profit by creating a new measure with formula:
   TotalProfit = (sum(Orders[Selling Price]) - sum(Orders[Product Cost])) * sum(Orders[Quantity])
2. This will give you the total profit made.
3. You can even create a new column under the table view section by using the above formula along with a new column name.
4. And the finally removing the aggregate funtion SUM for from the formula to get the individual data.(((Orders[Selling Price]) - (Orders[Product Cost])) * (Orders[Quantity]))
5. You can also add the product name under the column for profit cost to see which product made the highest profit by selling.


## using the if function to categorise the order size
Order Category = IF(Orders[Quantity] < 30, "Small Order", "Big Order")
