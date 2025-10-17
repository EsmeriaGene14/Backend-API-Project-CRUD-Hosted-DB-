# Inventory Store API

A complete RESTful API for inventory management system built with Node.js, Express, and MongoDB Atlas.

## Features

- Full CRUD operations for Products, Suppliers, and Orders
- MongoDB Atlas cloud database
- Pagination and filtering
- Proper error handling with HTTP status codes
- CORS enabled
- Environment variable security

## API Endpoints

### Base URL
\`http://localhost:3000\`

### Products

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | \`/api/products\` | Get all products with pagination |
| GET | \`/api/products/:id\` | Get single product by ID |
| POST | \`/api/products\` | Create new product |
| PUT | \`/api/products/:id\` | Update product |
| DELETE | \`/api/products/:id\` | Delete product |

### Suppliers

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | \`/api/suppliers\` | Get all suppliers with pagination |
| GET | \`/api/suppliers/:id\` | Get single supplier by ID |
| POST | \`/api/suppliers\` | Create new supplier |
| PUT | \`/api/suppliers/:id\` | Update supplier |
| DELETE | \`/api/suppliers/:id\` | Delete supplier |

### Orders

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | \`/api/orders\` | Get all orders with populated data |
| GET | \`/api/orders/:id\` | Get single order by ID |
| POST | \`/api/orders\` | Create new order |
| PUT | \`/api/orders/:id\` | Update order status |
| DELETE | \`/api/orders/:id\` | Delete order |

## 🛠️ Request Examples

### Get All Products
\`\`\`bash
GET http://localhost:3000/api/products
GET http://localhost:3000/api/products?page=1&limit=5
\`\`\`

### Create Product
<pre>
POST http://localhost:3000/api/products
Content-Type: application/json

{
      "_id": "68f0f88d5008a3e6e56b8e37",
      "sku": "LP-001",
      "name": "Laptop",
      "price": 159.99,
      "stock": 20,
      "createdAt": "2025-10-16T13:52:13.820Z",
      "updatedAt": "2025-10-16T13:52:13.820Z",
      "__v": 0
}
</pre>

### Create Supplier
<pre>
POST http://localhost:3000/api/suppliers
Content-Type: application/json

{
      "contact": {
        "email": "dev@gmail.com",
        "phone": "+639057156700"
      },
      "_id": "68f0f81d5008a3e6e56b8e1d",
      "name": "Dev Inc.",
      "createdAt": "2025-10-16T13:50:21.837Z",
      "updatedAt": "2025-10-16T13:50:21.837Z",
      "__v": 0
}
</pre>

### Create Order
<pre>
POST http://localhost:3000/api/orders
Content-Type: application/json
{
      "_id": "68f0f88d5008a3e6e56b8e37",
      "sku": "LP-001",
      "name": "Laptop",
      "price": 159.99,
      "stock": 20,
      "createdAt": "2025-10-16T13:52:13.820Z",
      "updatedAt": "2025-10-16T13:52:13.820Z",
      "__v": 0
    }
</pre>

## Project Structure


```
Inventory-Store-API/
├── config/
│   └── db.js
├── controllers/
│   ├── productController.js
│   ├── supplierController.js
│   └── orderController.js
├── models/
│   ├── Product.js
│   ├── Supplier.js
│   └── Order.js
├── routes/
│   ├── productRoutes.js
│   ├── supplierRoutes.js
│   └── orderRoutes.js
├── public/
│   ├── index.html
├── .env
├── .gitignore
├── app.js
├── package.json
├── package-lock.json
├── seedData.js
├── test-db.js
└── README.md
```

## Quick Start

1. **Clone and install dependencies:**
   \`\`\`bash
   npm install
   \`\`\`

2. **Set up environment variables:**
   Create \`.env\` file with:
   \`\`\`env
   PORT=3000
   MONGO_URI=your_mongodb_atlas_connection_string
   NODE_ENV=development
   \`\`\`

3. **Seed the database:**
   \`\`\`bash
   npm run seed
   \`\`\`

4. **Start the server:**
   \`\`\`bash
   npm run dev    # Development with auto-reload
   # or
   npm start      # Production
   \`\`\`

5. **Test the API:**
   Visit \`http://localhost:3000/api/products\`

## Environment Variables

- \`PORT\` - Server port (default: 3000)
- \`MONGO_URI\` - MongoDB Atlas connection string
- \`NODE_ENV\` - Environment mode

## Testing

Use the included Postman collection or test with:

\`\`\`bash
# Health check
curl http://localhost:3000/

# Get all products
curl http://localhost:3000/api/products
\`\`\`

## 📊 Sample Data

The seeder creates:
- 2 sample products
- 2 sample suppliers  
- 1 sample orders 

## Scripts

- \`npm start\` - Start production server
- \`npm run dev\` - Start development server with nodemon
- \`npm run seed\` - Populate database with sample data

## Security

- Environment variables for sensitive data
- Input validation on all endpoints
- Proper CORS configuration
- MongoDB Atlas with IP whitelisting

## License

ISC