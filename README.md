# Object Relational Mapping E-commerce

## Desctiption
We are building the back end of a e-commerce site. During this excercise we will be using Express.js and configure it to use Sequalize with a MySQL database.

## Demo
* Create Schema and Seed Data
https://drive.google.com/file/d/1wtfmQY0terMWOMhGJvxAEfu2-aEgTwnh/view
* The first animation shows GET routes to return all categories, all products, and all tags being tested in Insomnia Core:
https://drive.google.com/file/d/1G-6CGpzSu7DnCIzlJQwAvpSys8FnrhKa/view
* The second animation shows GET routes to return a single category, a single product, and a single tag being tested in Insomnia Core:
https://drive.google.com/file/d/1I9WA1TRctOBPHgLgfhJlBCTLb-1WBpUB/view
* This animation shows the POST, PUT, and DELETE routes for categories being tested in Insomnia Core:
https://drive.google.com/file/d/1UXwZ2l159ur7RFlXHJAvNqDFHnzm3FiT/view
* POST, PUT, and DELETE routes for products:
https://drive.google.com/file/d/1TEHnp4TJPIl5PKlRQEanDj1vu9Y7jPAL/view
* POST, PUT, and DELETE routes for tags:
https://drive.google.com/file/d/1kF-zyOj_swNYISywqZhrWEKAVAesVPug/view
## User Story
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies

## Acceptance Criteria
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database

## Database Models
* Category
    * id
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment
    * category_name
    * String
    * Doesn't allow null values

* Product
    * id
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment
    * product_name
    * String 
    * Doesn't allow null values
    * price
    * Decimal
    * Doesn't all null values
    * Validates that the value is a decimal
    * stock
    * Integer
    * Doesn't allow null values
    * Set a default value of 10
    * Validates that the value is numeric
    * category_id
    * Integer
    * References the category model's id

* Tag
    * id
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment
    * tag_name
    * String

* Product Tag
    * id
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment
    * product_id
    * Integer
    * References the product model's id
    * tag_id
    * Integer
    * References the tag model's id

## Associations
You'll need to execute association methods on your Sequelize models to create the following relationships between them:

    * Product belongs to Category
    * Category has many Product models.
    * Product belongs to many Tag models.
    * Tag belongs to many Product models.

## Instructions
* Add a .env file to the root of the app with the following details

DB_NAME='ecommerce_db'
DB_USER='root'
DB_PW='xxx'
