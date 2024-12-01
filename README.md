# Product Catalog Management - Graphy Assessment 

This repository provides a RESTful API for managing a product catalog, including CRUD operations, filtering capabilities, and caching. Built with **Spring Boot**, it leverages **Redis** for caching and includes comprehensive logging and metrics for monitoring.  

## Features  

1. **Retrieve All Products**  
   - Endpoint: `GET /productCatalog/getAllProducts`  
   - Fetches a list of all products in the catalog.  

2. **Retrieve Product by ID**  
   - Endpoint: `GET /productCatalog/getProduct/{id}`  
   - Fetches details of a single product by its unique ID.  

3. **Filter Products**  
   - Endpoint: `GET /productCatalog/filterProducts`  
   - Filters products by category and price range.  
   - **Query Parameters**:  
     - `category` (String): Product category to filter by.  
     - `priceMin` (Double): Minimum price.  
     - `priceMax` (Double): Maximum price.  

4. **Add a New Product**  
   - Endpoint: `POST /productCatalog/addProduct`  
   - Adds a new product to the catalog.  
   - **Request Body**:  
     ```json
     {
       "name": "Product Name",
       "category": "Category",
       "price": 99.99,
       "description": "Product Description"
     }
     ```  

5. **Update an Existing Product**  
   - Endpoint: `PUT /productCatalog/updateProduct/{id}`  
   - Updates details of an existing product by ID.  
   - **Request Body**:  
     ```json
     {
       "name": "Updated Product Name",
       "category": "Updated Category",
       "price": 149.99,
       "description": "Updated Product Description"
     }
     ```  

6. **Delete a Product**  
   - Endpoint: `DELETE /productCatalog/deleteProduct/{id}`  
   - Deletes a product from the catalog by its ID.  

## Logging and Metrics  

- **Logging**:  
  - Logs are managed using **SLF4J**.  
  - Includes detailed logs for API calls, cache operations, and error handling.  

- **Metrics**:  
  - Metrics are tracked using **Micrometer**.  
  - Tracks:  
    - **Cache Hits** (`cache.hit`)  
    - **Cache Misses** (`cache.miss`)  

## Caching  

- **Redis** is used for caching product data to improve performance.  
- Cache entries have a **TTL (Time to Live)** of 10 minutes, configured in `RedisConfig`.  
- The cache operations are handled via **Spring's Cache Abstraction**.  

## License  

This project is open-source and available under the [MIT License](LICENSE).
