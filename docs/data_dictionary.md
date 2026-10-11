# Data Dictionary

## 1. Customers

**Table description:** Contains customer records associated with orders, including customer identifiers and location information.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `customer_id` | String | PK | Unique identifier for a customer record associated with an order. |
| `customer_unique_id` | String | | Identifier representing a unique customer across customer records. |
| `customer_zip_code_prefix` | String | | Prefix of the customer's ZIP code, used for geographic analysis. |
| `customer_city` | String | | City associated with the customer record. |
| `customer_state` | String | | State associated with the customer record. |

## 2. Orders

**Table description:** Contains order-level information, including order status and timestamps throughout the order lifecycle.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `order_id` | String | PK | Unique identifier for an order. |
| `customer_id` | String | FK | Identifier linking the order to a customer record. |
| `order_status` | String | | Current recorded status of the order. |
| `order_purchase_timestamp` | Datetime | | Timestamp when the order was placed. |
| `order_approved_at` | Datetime | | Timestamp when the order was approved. |
| `order_delivered_carrier_date` | Datetime | | Timestamp when the order was handed over to the carrier. |
| `order_delivered_customer_date` | Datetime | | Timestamp when the order was delivered to the customer. |
| `order_estimated_delivery_date` | Datetime | | Estimated delivery date provided for the order. |

## 3. Order Items

**Table description:** Contains individual items included in each order, including product, seller, price, and freight information.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `order_id` | String | PK, FK | Identifier of the order containing the item. |
| `order_item_id` | Integer | PK | Sequential item number within an order. |
| `product_id` | String | FK | Identifier of the product included in the order. |
| `seller_id` | String | FK | Identifier of the seller associated with the item. |
| `shipping_limit_date` | Datetime | | Deadline for the seller to hand the item over for shipping. |
| `price` | Float | | Price of the item. |
| `freight_value` | Float | | Freight cost associated with the item. |

## 4. Order Payments

**Table description:** Contains payment records associated with orders.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `order_id` | String | PK, FK | Identifier of the order associated with the payment. |
| `payment_sequential` | Integer | PK | Sequential number identifying a payment record within an order. |
| `payment_type` | String | | Payment method used for the transaction. |
| `payment_installments` | Integer | | Number of installments selected for the payment. |
| `payment_value` | Float | | Monetary value recorded for the payment. |

## 5. Order Reviews

**Table description:** Contains customer review information associated with orders.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `review_id` | String | | Identifier assigned to a review. It is not treated as a unique primary key because duplicate values were observed during exploration. |
| `order_id` | String | FK | Identifier of the order associated with the review. |
| `review_score` | Integer | | Customer rating score for the order. |
| `review_comment_title` | String | | Title of the customer's review, when provided. |
| `review_comment_message` | String | | Text content of the customer's review, when provided. |
| `review_creation_date` | Datetime | | Timestamp indicating when the review survey was created. |
| `review_answer_timestamp` | Datetime | | Timestamp indicating when the review was submitted or answered. |

## 6. Products

**Table description:** Contains product attributes, category information, and physical dimensions.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `product_id` | String | PK | Unique identifier for a product. |
| `product_category_name` | String | FK | Product category name in Portuguese, when available. |
| `product_name_lenght` | Integer | | Length of the product name. |
| `product_description_lenght` | Integer | | Length of the product description. |
| `product_photos_qty` | Integer | | Number of product photos. |
| `product_weight_g` | Integer | | Product weight in grams. |
| `product_length_cm` | Integer | | Product length in centimeters. |
| `product_height_cm` | Integer | | Product height in centimeters. |
| `product_width_cm` | Integer | | Product width in centimeters. |

## 7. Sellers

**Table description:** Contains seller identifiers and location information.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `seller_id` | String | PK | Unique identifier for a seller. |
| `seller_zip_code_prefix` | String | | Prefix of the seller's ZIP code. |
| `seller_city` | String | | City associated with the seller. |
| `seller_state` | String | | State associated with the seller. |

## 8. Geolocation

**Table description:** Contains geographic coordinates and location names associated with ZIP code prefixes.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `geolocation_zip_code_prefix` | String | | ZIP code prefix associated with a geographic record. This field is not unique. |
| `geolocation_lat` | Float | | Latitude of the geographic record. |
| `geolocation_lng` | Float | | Longitude of the geographic record. |
| `geolocation_city` | String | | City name associated with the geographic record. |
| `geolocation_state` | String | | State abbreviation associated with the geographic record. |

## 9. Product Category Translation

**Table description:** Maps Portuguese product category names to English translations.

| Column | Data Type | Key | Description |
|---|---|---|---|
| `product_category_name` | String | PK | Product category name in Portuguese, used to match the products table. |
| `product_category_name_english` | String | | English translation of the product category name. |