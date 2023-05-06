# E-Commerce Back End Application

![license](https://img.shields.io/badge/license-MIT-green)

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Future Development](#future-development)
- [License](#license)

## Description

Node web application using Sequelize, Express, and MySQL2 to create a backend application for storing, organizing, and maintaining a basic inventory system.

## Features

* Provides an easy way to maintain a simple inventory database
* Ability to add new Categories, Products, and Tags
* Ability to update Categories, Products, and Tags

## Installation

- Ensure Node, npm, and MySQL (or another SQL CLI application) are installed
- Create a `.env` file similar to the example file provided; include root user login information for mysql connection
- Run `npm i` to install required dependencies
- Run `MySQL -u root -p` to launch MySQL (or start another SQL CLI program)
- Run `SOURCE db/schema.sql` to initialize the database with the correct schema
- Run `node seeds/index.js` to seed the data base with the sample data
- Run `npm start` or `Node server.js` to start the program

## Usage

This program can be used to maintain a simple inventory database. To initialize the database, `db/schema.sql` and `seeds` files are provided to fill the database with sample data. Be sure to follow the [Installation](#installation) instructions above.

Upon initialization, access the database using the following web addresses (assuming localhost:3001 or hosted location as root)

Demonstration of these api calls can be seen [here](https://youtu.be/I6yGO84vzNo)

###### Categories

* `GET /api/categories/` 		Returns all categories with their associated products
* `GET /api/categories/:id`		Returns the specified category with associated products
* `POST /api/categories/`		Adds a new category to the database ***body required***
* `PUT /api/categories/:id`		Renames the specified category ***body required***
* `DELETE /api/categories/:id`	Removes the specified category from the database

*body must contain an object with the* `"category_name"` *field defined*

###### Products

* `GET /api/products/`			returns all products with their associated categories and tags
* `GET /api/products/:id`		returns the specified product with associated categories and tags
* `POST /api/products/`			Adds a new product to the database - ***body required***
* `PUT /api/products/:id`		Updates the specified product with new information - ***body required***
* `DELETE /api/products/:id`		Removes the specified product from the database

*body must contain an object with the following fields defined:*

* `"product_name"` : string
* `"price"` : float
* `"stock"` : int
* `"category_id"` : int (category PK)
* `"tagIds"` : Array of tag ids

###### Tags

* `GET /api/tags/`				Returns all tags with their associated products
* `GET /api/tags/:id`			Returns the specified tag with associated products
* `POST /api/tags/`			Adds a new tag to the database - ***body required***
* `PUT /api/tags/:id`			Updates the specified tag with new information - ***body required***
* `DELETE /api/tags/:id`		Removes the specified tag from the database

*body must contain an object with the* `"tag_name"` *field defined*

## License

 Please refer to the [LICENSE](./LICENSE) in the repo.
