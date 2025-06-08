# CLeaning de données avec PySpark

## Avant de démarrer

S'assurer d'avoir Java 17

## Étape 1

créer un venv en python 3.9.6
Importer les packages avec requirements.txt

## Étape 2

Verifications du dataset (doublons, valeurs null, stats etc)

## Étape 3 

Suivre cette consigne

| column            | data type | description                                                                 | cleaning requirements                                                                                                                                                   |
|-------------------|------------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `order_date`       | timestamp  | Date and time when the order was made                                       | *Modify*: Remove orders placed between 12am and 5am (inclusive); convert from timestamp to date                                                                         |
| `time_of_day`      | string     | Period of the day when the order was made                                   | *New column* containing (lower bound inclusive, upper bound exclusive): "morning" for orders placed 5-12am, "afternoon" for orders placed 12-6pm, and "evening" for 6-12pm |
| `order_id`         | long       | Order ID                                                                    | N/A                                                                                                                                                                      |
| `product`          | string     | Name of a product ordered                                                   | *Remove* rows containing "TV" as the company has stopped selling this product; ensure all values are lowercase                                                          |
| `product_ean`      | double     | Product ID                                                                  | N/A                                                                                                                                                                      |
| `category`         | string     | Broader category of a product                                               | Ensure all values are lowercase                                                                                                                                          |
| `purchase_address` | string     | Address line where the order was made ("House Street, City, State Zipcode")| N/A                                                                                                                                                                      |
| `purchase_state`   | string     | US State of the purchase address                                            | *New column* containing: the State that the purchase was ordered from                                                                                                    |
| `quantity_ordered` | long       | Number of product units ordered                                             | N/A                                                                                                                                                                      |
| `price_each`       | double     | Price of a product unit                                                     | N/A                                                                                                                                                                      |
| `cost_price`       | double     | Cost of production per product unit                                         | N/A                                                                                                                                                                      |
| `turnover`         | double     | Total amount paid for a product (quantity x price)                          | N/A                                                                                                                                                                      |
| `margin`           | double     | Profit made by selling a product (turnover - cost)                          | N/A                                                                                                                                                                      |
