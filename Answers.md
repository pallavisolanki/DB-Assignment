## Answer #1:

The relationship between the “Product” and “Product_Category” entities is a many-to-one relationship. Let me explain:

1. In a many-to-one relationship, multiple instances of one entity (in this case, products) can be associated with a single instance of another entity (product category).

   Here’s how it applies to our scenario:
   - “Product” (many): Each product (e.g., a smartphone, a laptop) corresponds to a separate row in the “Product” table.
   - “Product_Category” (one): The product categories (e.g., Electronics, Apparel) are represented as rows in the “Product_Category” table.
   
   The “category_id” attribute in the “Product” table acts as a foreign key, linking each product to its corresponding category.

2. Suppose we have the following data:
   - Product 1: Smartphone (category_id = 1, belongs to Electronics)
   - Product 2: Laptop (category_id = 1, also belongs to Electronics)
   - Product 3: T-shirt (category_id = 2, belongs to Apparel)
   
   In this example:
   - Both the smartphone and laptop share the same category (Electronics), forming a many-to-one relationship.
   - The T-shirt belongs to a different category (Apparel).

---

## Answer #2:

To ensure that each product in the “Product” table has a valid category assigned, you can implement the following strategies:

1. Using Foreign Key:
   - Define a foreign key relationship between the “Product” table and the “Product_Category” table.
   - The “category_id” column in the “Product” table should reference the primary key “id” in the “Product_Category” table.
   - This constraint ensures that any value in the “category_id” column must exist as a valid category ID in the “Product_Category” table.

2. Using Trigger and Stored Procedure:
   - Create triggers or stored procedures that run whenever a new product is inserted or updated.
   - These triggers can check whether the specified “category_id” exists in the “Product_Category” table.
   - If not, raise an error or handle the situation appropriately.
