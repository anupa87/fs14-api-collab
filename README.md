# E-commerce API documentation from Group 5

## 1. What the data will look like

### Products:

- productId: unique identifier of the product.
- productName: title of product, not neccesarily unique but should be.
- description: descriptor in sentence or sentences, of the product.
- categories: a single, or set of descriptors of the product from a set of descriptors decided between the developer and customer 
- size: a single descriptor of the product according to an established size (s, m, l, xl)
- price: numerical representation of price in two decimal precision (i.e. 12.29)

### Users:

- userId: unique identifier of user
- firstName: first name of user
- lastName: last name of user
- email: email address, must be unique
- password: password which meets requirements set by server
- role: descriptor of user's role, to establish what action they can perform in the REST API

### Orders:

- orderId: unique identifier of order
- productId: identifies the product purchased
- quantity: amount of products requested
- email: which user created the order
- createdAt: a UTC timestamp of when the order was saved in the database

there can be multiple entries with the same orderId, but the productId must be different. due to this, the orderId and productId combined will serve as the unique identifier of the entry (aka composite key).

## 2. What entities the API will have

The entities that the API will have are Products, Users and Orders.

## 3. What is relation between entities

There are two relationships:
- Each user can have many orders
- Each order can have many products

## 4. What kind of endpoints the API will have

This will be decided based on the needed actions. So far, the actions are:

### /products

1. GET request - get all products in the database. query strings can be appended to narrow the search, to paginate, filter (size, categories, price), and sort attribute. returns a mapping of products.
2. POST request - add a new product to the database with the above mentioned attributes.

### /products/:productId

1. GET request- get a product according to it's unique identifier. returns one object.
2. PATCH request - updates a product with it's identifier. returns updated item and 200 http code.
3. DELETE request - remove a product according to it's identifier. returns 200 http code.

### /auth

1. POST request - creates an access token for the user to sign in, if the credentials are correctly filled.

### /users

1. POST request - create (sign up) a new user in the database. returns 200 code, and user will need to sign to get access token.

### /users/:userId

1. PATCH request - user can change their first name, last name or email address


## 5. Swagger output

# Design a REST API - Design First (NO CODE)

Before diving into the assignment, make sure you review the slides and understand the theortical part and best practices.

## Plan with your group mates:

- What my data should look like
- What are the entities that we should have ie (Products and Users)
- What is the relation between these entities (you could read about it, and we will cover that in the next lectures)
- What kind of endpoints the API would have
- Document the endpoints using Swagger (documentation only, NO CODE)

Make sure you cover the basic routes first.
