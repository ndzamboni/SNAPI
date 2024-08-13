# eCommerce Back End - Initial Version

This project is the initial back end for an eCommerce application. It includes a functional Express.js API, PostgreSQL database connection, and Sequelize ORM to manage database interactions. This version focuses on creating, reading, updating, and deleting categories, products, and tags.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Database Schema](#database-schema)
- [Database Models](#database-models)
- [API Endpoints](#api-endpoints)
  - [Categories](#categories)
  - [Products](#products)
  - [Tags](#tags)
- [Testing API Routes in Insomnia](#testing-api-routes-in-insomnia)
- [Seeding the Database](#seeding-the-database)
- [License](#license)

## Installation

1. **Clone the Repository:**

    ```bash
    git clone git@work.github.com:coding-boot-camp/module-13-challenge-orm.git
    ```

2. **Navigate to the Project Directory:**

    ```bash
    cd module-13-challenge-orm/develop
    ```

3. **Install Dependencies:**

    ```bash
    npm install
    ```

4. **Set Up Environment Variables:**

    Create a `.env` file in the `develop` directory with the following content:

    ```env
    DB_NAME='ecommerce_db'
    DB_USER='your_postgres_username'
    DB_PASSWORD='your_postgres_password'
    ```

5. **Create the Database:**

    Use the `schema.sql` file to create the necessary database structure. Run the following command in your PostgreSQL shell:

    ```sql
    \i path_to_your_project/develop/db/schema.sql
    ```

## Usage

1. **Seed the Database:**

    To populate your database with initial data, run:

    ```bash
    npm run seed
    ```

2. **Start the Server:**

    To start the server, run:

    ```bash
    npm start
    ```

    The server will be running on `http://localhost:3001`.

## Database Schema

The database schema consists of four tables:

1. **Categories Table:**

    - `id`: Integer, primary key, auto-incremented.
    - `category_name`: String, not nullable.

2. **Products Table:**

    - `id`: Integer, primary key, auto-incremented.
    - `product_name`: String, not nullable.
    - `price`: Decimal, not nullable, validates that the value is a decimal.
    - `stock`: Integer, not nullable, default value of 10, validates that the value is numeric.
    - `category_id`: Integer, foreign key, references the `id` column in the `categories` table.

3. **Tags Table:**

    - `id`: Integer, primary key, auto-incremented.
    - `tag_name`: String.

4. **ProductTags Table:**

    - `id`: Integer, primary key, auto-incremented.
    - `product_id`: Integer, foreign key, references the `id` column in the `products` table.
    - `tag_id`: Integer, foreign key, references the `id` column in the `tags` table.

## Database Models

The Sequelize models correspond to the tables in the database:

1. **Category Model:**

    - Represents the `categories` table.
    - Fields: `id`, `category_name`.

2. **Product Model:**

    - Represents the `products` table.
    - Fields: `id`, `product_name`, `price`, `stock`, `category_id`.

3. **Tag Model:**

    - Represents the `tags` table.
    - Fields: `id`, `tag_name`.

4. **ProductTag Model:**

    - Represents the `product_tags` table.
    - Fields: `id`, `product_id`, `tag_id`.

## API Endpoints

### Categories

- **GET /api/categories**: Get all categories with their associated products.
- **GET /api/categories/:id**: Get a single category by its ID with its associated products.
- **POST /api/categories**: Create a new category.
- **PUT /api/categories/:id**: Update a category by its ID.
- **DELETE /api/categories/:id**: Delete a category by its ID.

### Products

- **GET /api/products**: Get all products with their associated category and tags.
- **GET /api/products/:id**: Get a single product by its ID with its associated category and tags.
- **POST /api/products**: Create a new product. The request body should look like this:

    ```json
    {
      "product_name": "Basketball",
      "price": 200.00,
      "stock": 3,
      "tagIds": [1, 2, 3, 4]
    }
    ```

- **PUT /api/products/:id**: Update a product by its ID.
- **DELETE /api/products/:id**: Delete a product by its ID.

### Tags

- **GET /api/tags**: Get all tags with their associated products.
- **GET /api/tags/:id**: Get a single tag by its ID with its associated products.
- **POST /api/tags**: Create a new tag.
- **PUT /api/tags/:id**: Update a tag by its ID.
- **DELETE /api/tags/:id**: Delete a tag by its ID.

## Testing API Routes in Insomnia

To test the API routes using Insomnia, follow these steps:

1. **Open Insomnia** and create a new workspace for your eCommerce API.

2. **Create requests** for each API endpoint under the appropriate folders (e.g., "Categories", "Products", "Tags").

3. **For each request:**

    - **GET Requests:** Send the request to view the data.
    - **POST Requests:** Include a JSON body with the necessary data to create a new entry.
    - **PUT Requests:** Include a JSON body to update an existing entry.
    - **DELETE Requests:** Send the request to delete an entry by ID.

4. **Review the JSON responses** to ensure that the API is functioning as expected.

## Tech Stack

- **Node.js**: JavaScript runtime environment.
- **Express.js**: Web application framework for Node.js.
- **PostgreSQL**: Relational database management system.
- **Sequelize**: Promise-based Node.js ORM for PostgreSQL.
- **dotenv**: Module for loading environment variables from a `.env` file.

## About Me

I am a software developer with experience in building full-stack applications. My expertise includes working with modern web technologies such as Node.js, Express.js, and various databases. I enjoy solving complex problems and am passionate about learning new technologies to improve my skill set.

## License

This project is licensed under the MIT License.
