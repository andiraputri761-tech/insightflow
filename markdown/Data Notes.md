# InsightFlow: Data Exploration Notes

## 1. Dataset Overview
- Dataset name: Brazilian E-Commerce Public Dataset by Olist
- Source: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
- Table count: 9
- Transaction period: 2016 - 2018
- Total orders: 99441

## 2. Data Quality
- Tables with missing values: 3 (Reviews, orders, products)
- Tables with duplicates data: 1 (Geolocation)

## 3. Table Relationships

- orders ke order_items:
- orders ke customers:
- order_items ke products:
- order_items ke sellers:

## 4. Initial Findings
### (1)
 Geolocation duplicates might occur because one zip code maps to multiple regions and coordinates. We must investigate this issue further.

### (2)  
Missing values are found in the review table:
- review_comment_title: 87.656 missing values.
- review_comment_message: 58.247 missing values.
This findings are very reasonable, we can leave these fields empty since the ratings remain useful.

### (3)
Missing values are also found in orders table:
- order_delivered_customer_date: 2.965.
- order_delivered_carrier_date: 1.783.
- order_approved_at: 160.
Unfinished or canceled orders likely caused these issues. We must check the order status before handling them.

### (4)
Products table also have missing values:
- product_category_name, product_name_lenght product_description_lenght, product_photos_qty (610 missing values)
- product_weight_g, product_length_cm, product_height_cm, product_width_cm (2 missing values)
We must verify if those 610 rows originate from identical products and if the missing attributes impact category analysis or machine learning models.


## 5. Follow-up Actions

- [ ] Validasi tipe data tanggal
- [ ] Periksa duplikasi ID
- [ ] Tentukan strategi penanganan missing values
- [ ] Siapkan data untuk analisis KPI