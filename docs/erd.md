
erDiagram
    CUSTOMERS ||--o{ ORDERS : places
    ORDERS ||--|{ ORDER_ITEMS : contains
    ORDERS ||--o{ ORDER_PAYMENTS : has
    ORDERS ||--o{ ORDER_REVIEWS : receives
    PRODUCTS ||--o{ ORDER_ITEMS : included_in
    SELLERS ||--o{ ORDER_ITEMS : fulfills
    PRODUCT_CATEGORY_TRANSLATION o|--o{ PRODUCTS : translates
    CUSTOMERS }o..o{ GEOLOCATION : zip_prefix
    SELLERS }o..o{ GEOLOCATION : zip_prefix

    CUSTOMERS {
        string customer_id PK
        string customer_unique_id
        string customer_zip_code_prefix
        string customer_city
        string customer_state
    }

    ORDERS {
        string order_id PK
        string customer_id FK
        string order_status
        datetime order_purchase_timestamp
        datetime order_approved_at
        datetime order_delivered_carrier_date
        datetime order_delivered_customer_date
        datetime order_estimated_delivery_date
    }

    ORDER_ITEMS {
        string order_id PK, FK
        int order_item_id PK
        string product_id FK
        string seller_id FK
        datetime shipping_limit_date
        float price
        float freight_value
    }

    ORDER_PAYMENTS {
        string order_id PK, FK
        int payment_sequential PK
        string payment_type
        int payment_installments
        float payment_value
    }

    ORDER_REVIEWS {
        string review_id
        string order_id FK
        int review_score
        datetime review_creation_date
        datetime review_answer_timestamp
    }

    PRODUCTS {
        string product_id PK
        string product_category_name FK
        int product_name_lenght
        int product_description_lenght
        int product_photos_qty
        int product_weight_g
        int product_length_cm
        int product_height_cm
        int product_width_cm
    }

    SELLERS {
        string seller_id PK
        string seller_zip_code_prefix
        string seller_city
        string seller_state
    }

    PRODUCT_CATEGORY_TRANSLATION {
        string product_category_name PK
        string product_category_name_english
    }

    GEOLOCATION {
        string geolocation_zip_code_prefix
        float geolocation_lat
        float geolocation_lng
        string geolocation_city
        string geolocation_state
    }


## ERD Overview

The Entity Relationship Diagram (ERD) represents the relationships among the nine tables in the Olist Brazilian E-Commerce dataset.

The `orders` table serves as the central table for order-level analysis. It connects customer records with order items, payment records, and customer reviews. The `order_items` table connects orders with products and sellers, supporting product-level and seller-level performance analysis.

The `product_category_name_translation` table provides English translations for product category names. The `geolocation` table contains geographic coordinates associated with ZIP code prefixes and requires additional mapping before it can be reliably integrated into analytical datasets.

### Key Design Considerations

- **Composite keys:** `order_items` uses `order_id` and `order_item_id`, while `order_payments` uses `order_id` and `payment_sequential` to identify individual records.
- **Review records:** `review_id` is not assumed to be unique because duplicate values were identified during data exploration.
- **Geolocation mapping:** ZIP code prefixes are not unique in the geolocation table. A suitable mapping strategy is required before joining this table with customer or seller data.
- **Analytical grain:** Order-level and item-level data must be handled separately when calculating KPIs to prevent double counting during joins.