# e-commerce-project

__Research of online store product metrics__

__There are six problems to be solved:__

1. How many users have made a purchase only once?
2. How many orders per month on average are not delivered for various reasons (detail the reasons)?
3. For each product, determine on what day of the week the product is most often purchased.
4. How many purchases does each user have on average per week (by month)?
5. Conduct a cohort analysis of users. In the period from January to December, identify the cohort with the highest retention in the 3rd month.
6. Build RFM user segmentation to qualitatively assess the audience.


__Data Description:__
*Files and their contents:*

__olist_customers_datase — table with unique user IDs__
customer_id — custom user identifier
customer_unique_id - unique user identifier (analogous to a passport number)
customer_zip_code_prefix - user's zip code
customer_city — user's delivery city
customer_state — user's delivery state

__olist_orders_dataset —  order table__
order_id — unique order identifier (receipt number)
customer_id — custom user identifier
order_status — order status
order_purchase_timestamp — order creation time
order_approved_at — order payment confirmation time
order_delivered_carrier_date — time of delivery of the order to the logistics service
order_delivered_customer_date — order delivery time
order_estimated_delivery_date — promised delivery date

__olist_order_items_dataset —  product items included in orders__
order_id — unique order identifier (receipt number)
order_item_id — product identifier within one order
product_id — product id (analogous to a barcode)
seller_id — id of the product manufacturer
shipping_limit_date — maximum delivery date for the seller to transfer the order to the logistics partner
price — price per unit of goods
freight_value — weight of the goods

__Stack used:__
Python
pandas 
numpy 
scipy
seaborn 
matplotlib


__Results:__

0. Research and data preparation carried out
1. The number of unique users who made a purchase once was determined - 91,804 users
2. Since most orders are in “statuses”, which are normal stages of order processing, we only take into account the statuses: *unavailable* and *canceled*. On average, orders are not delivered per month for the following reasons: unavailable (29 orders) and canceled (26 orders).
3. Product_id is determined with a breakdown by day and maximum number of orders
4. A table and a bar chart displaying user indices and the average number of purchases are displayed.
5. A cohort analysis with visualization was carried out and a cohort with the highest retention in the 3rd month was discovered - 2017-05, 0.003972.
6. The following RFM segmentation has been implemented:
  Based on the information received, we distribute the RFM values as follows:
__Recency__
1 - ordered not long ago (0 - 189)
2 - client in "idle" (190 - 359)
3 - ordered a long time ago (360 - 727)
__Frequency__
3 - bought little (0-1)
2 - bought medium (1-2)
1 - bought a lot (2-16)
__Monetary__
3 - small check (0-90)
2 - average check (90-350)
1 - large check (350-13441)
   
__Based on the results obtained, we can conclude that most users buy few goods and for a small amount, and most users often buy in the range from 0 to 359 days.
For clarity of RFM distribution, the TOP 15 RFM groups by number of users were made.__
