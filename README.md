# Product API

A simple Express.js REST API for managing products.

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- [pnpm](https://pnpm.io/) (or npm/yarn)

## Setup

1. Clone the repository and navigate into the directory:
   ```bash
   cd express-api
   ```

2. Install dependencies:
   ```bash
   pnpm install
   ```

3. Environment variables are pre-configured in `.env`. Adjust if needed:
   ```
   NODE_ENV=development
   API_VERSION=v1
   ```

## Running the server

### Production mode
```bash
pnpm start
```

### Development mode (with auto-reload)
```bash
pnpm dev
```

The server starts on `http://localhost:3000` by default (or the port defined in the `PORT` environment variable).

## Testing the API locally

You can test the API using `curl` or any HTTP client (Postman, Insomnia, etc.).

### Health check
```bash
curl http://localhost:3000/health
```

### Get all products
```bash
curl http://localhost:3000/products
```

### Get paginated products
```bash
curl "http://localhost:3000/products/paginated?page=1&limit=2"
```

### Get a single product by ID
```bash
curl http://localhost:3000/products/1
```

### Create a new product
```bash
curl -X POST http://localhost:3000/products \
  -H "Content-Type: application/json" \
  -d '{"name":"Tablet","price":399.99,"stock":75}'
```

### Update a product
```bash
curl -X PUT http://localhost:3000/products/1 \
  -H "Content-Type: application/json" \
  -d '{"name":"Gaming Laptop","price":1299.99,"stock":30}'
```

### Delete a product
```bash
curl -X DELETE http://localhost:3000/products/1
```
