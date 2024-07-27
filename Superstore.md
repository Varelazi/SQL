**Schema (MySQL v5.7)**

    CREATE TABLE superstore (
        item_id INTEGER PRIMARY KEY,
        item_name TEXT,
        category TEXT,
        price DECIMAL(10, 2),
        stock_quantity INTEGER,
        average_rating DECIMAL(3, 2)
    );
    
    INSERT INTO superstore (item_id, item_name, category, price, stock_quantity, average_rating)
    VALUES
        (1, 'Stainless Steel Cookware Set', 'Kitchen Supplies', 89.99, 50, 4.6),
        (2, 'Memory Foam Mattress', 'Furnishings', 499.99, 30, 4.8),
        (3, 'Smart LED TV', 'Electronics', 549.00, 20, 4.5),
        (4, 'Robot Vacuum Cleaner', 'Appliances', 199.50, 40, 4.3),
        (5, 'Wireless Bluetooth Speaker', 'Electronics', 39.99, 60, 4.2),
        (6, 'Non-Stick Baking Set', 'Kitchen Supplies', 29.95, 80, 4.4),
        (7, 'Cotton Bedding Set', 'Furnishings', 89.00, 25, 4.7),
        (8, 'Smart Home Security Camera', 'Electronics', 79.95, 15, 4.1),
        (9, 'Air Purifier', 'Appliances', 129.50, 35, 4.6),
        (10, 'Premium Coffee Maker', 'Kitchen Supplies', 79.99, 50, 4.9),
        (11, 'Ergonomic Office Chair', 'Furnishings', 189.00, 20, 4.5),
        (12, 'Wireless Earbuds', 'Electronics', 49.99, 75, 4.3),
        (13, 'Slow Cooker', 'Appliances', 49.95, 30, 4.7),
        (14, 'Cutlery Set', 'Kitchen Supplies', 34.50, 40, 4.4),
        (15, 'Cozy Throw Blanket', 'Furnishings', 24.99, 100, 4.2);
    

---

**Query #1**
### Prompt One - Write a SQL query that orders the items by price.

    SELECT item_name,
    price
    FROM superstore
    ORDER BY price ASC;

        | item_name                    | price  |
        | ---------------------------- | ------ |
        | Cozy Throw Blanket           | 24.99  |
        | Non-Stick Baking Set         | 29.95  |
        | Cutlery Set                  | 34.50  |
        | Wireless Bluetooth Speaker   | 39.99  |
        | Slow Cooker                  | 49.95  |
        | Wireless Earbuds             | 49.99  |
        | Smart Home Security Camera   | 79.95  |
        | Premium Coffee Maker         | 79.99  |
        | Cotton Bedding Set           | 89.00  |
        | Stainless Steel Cookware Set | 89.99  |
        | Air Purifier                 | 129.50 |
        | Ergonomic Office Chair       | 189.00 |
        | Robot Vacuum Cleaner         | 199.50 |
        | Memory Foam Mattress         | 499.99 |
        | Smart LED TV                 | 549.00 |

---
**Query #2**
### Prompt Two - Write your own SQL query that will show a statistic about the item prices, like a sum, average, minimum, maximum, or count. 
NOTE: I used all of the statistics for my answer including the following prompts.

    SELECT SUM(price), 
    AVG(price), 
    MAX(price),
    MIN(price),
    COUNT(price)
    FROM superstore;

        | SUM(price) | AVG(price) | MAX(price) | MIN(price) | COUNT(price) |
        | ---------- | ---------- | ---------- | ---------- | ------------ |
        | 2135.29    | 142.352667 | 549.00     | 24.99      | 15           |

---
**Query #3**
### Prompt Three - Write your own SQL query that will show a statistic about the price for items in the category of "Kitchen Supplies". NOTE: The values in the categories column are called text strings, and text strings are case sensitive. That means if you want to select "Kitchen Supplies", you will need to type it exactly as it appears in the data, i.e., with a capital "K" and a capital "S".

    SELECT SUM(price),
    AVG(price), 
    MAX(price),
    MIN(price),
    COUNT(price)
    FROM superstore
    WHERE category='Kitchen Supplies';

        | SUM(price) | AVG(price) | MAX(price) | MIN(price) | COUNT(price) |
        | ---------- | ---------- | ---------- | ---------- | ------------ |
        | 234.43     | 58.607500  | 89.99      | 29.95      | 4            |

---
**Query #4** 
- Come up with your own question about the data and try to answer it using SQL. For example: How many air purifiers are in stock?
### Prompt Four - Order the items by their rating. From best to least rated item.

    SELECT item_name,
    average_rating
    FROM superstore
    ORDER BY average_rating DESC;

        | item_name                    | average_rating |
        | ---------------------------- | -------------- |
        | Premium Coffee Maker         | 4.90           |
        | Memory Foam Mattress         | 4.80           |
        | Cotton Bedding Set           | 4.70           |
        | Slow Cooker                  | 4.70           |
        | Stainless Steel Cookware Set | 4.60           |
        | Air Purifier                 | 4.60           |
        | Smart LED TV                 | 4.50           |
        | Ergonomic Office Chair       | 4.50           |
        | Non-Stick Baking Set         | 4.40           |
        | Cutlery Set                  | 4.40           |
        | Robot Vacuum Cleaner         | 4.30           |
        | Wireless Earbuds             | 4.30           |
        | Wireless Bluetooth Speaker   | 4.20           |
        | Cozy Throw Blanket           | 4.20           |
        | Smart Home Security Camera   | 4.10           |

---

[View on DB Fiddle](https://www.db-fiddle.com/f/PvBAaQwEUSWAxZCsg4Vmx/0)