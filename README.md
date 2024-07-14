# MongoDB Product Queries

This project contains MongoDB queries for managing a product database. Below are the details of the available queries and their purposes.

## Prerequisites

- MongoDB installed and running
- MongoDB Shell or any MongoDB GUI (e.g., MongoDB Compass)

## Product Data

Here is the sample JSON data used in this project:

```json
[
    {
        "id": "1",
        "product_name": "Intelligent Fresh Chips",
        "product_price": 655.00,
        "product_material": "Concrete",
        "product_color": "mint green"
    },
    {
        "id": "2",
        "product_name": "Practical Fresh Sausages",
        "product_price": 911.0,
        "product_material": "Cotton",
        "product_color": "indigo"
    },
    ...
]


Here's a sample README.md file for your MongoDB project:

markdown
Copy code
# MongoDB Product Queries

This project contains MongoDB queries for managing a product database. Below are the details of the available queries and their purposes.

## Prerequisites

- MongoDB installed and running
- MongoDB Shell or any MongoDB GUI (e.g., MongoDB Compass)

## Product Data

Here is the sample JSON data used in this project:

```json
[
    {
        "id": "1",
        "product_name": "Intelligent Fresh Chips",
        "product_price": 655.00,
        "product_material": "Concrete",
        "product_color": "mint green"
    },
    {
        "id": "2",
        "product_name": "Practical Fresh Sausages",
        "product_price": 911.0,
        "product_material": "Cotton",
        "product_color": "indigo"
    },
    ...
]


Queries
1. Find all the information about each product
json

db.products.find({})
2. Find the product price which are between 400 to 800
json

db.products.find({ product_price: { $gte: 400, $lte: 800 } }, { product_price: 1, _id: 0 })
3. Find the product price which are not between 400 to 600
json

db.products.find({ product_price: { $not: { $gte: 400, $lte: 600 } } }, { product_price: 1, _id: 0 })
4. List the four products which are greater than 500 in price
json

db.products.find({ product_price: { $gt: 500 } }).limit(4)
5. Find the product name and product material of each product
json

db.products.find({}, { product_name: 1, product_material: 1, _id: 0 })


6. Find the product with a row id of 10
json

db.products.find({ id: "10" })


7. Find only the product name and product material
json

db.products.find({}, { product_name: 1, product_material: 1, _id: 0 })


8. Find all products which contain the value "soft" in product material
json
db.products.find({ product_material: /soft/i })


9. Find products which contain product color "indigo" and product price 492.00
json

db.products.find({ product_color: "indigo", product_price: 492.00 })


10. Delete the products which product price value is 28
json

db.products.deleteMany({ product_price: 28 })
