# Food Delivery Website - Backend

## Setup Instructions

### 1. Install MongoDB
Make sure MongoDB is installed and running on your system.

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Update the `.env` file with your configurations:
- `JWT_SECRET`: Your JWT secret key
- `MONGODB_URI`: Your MongoDB connection string (default: mongodb://localhost:27017/food-delivery)
- `PORT`: Server port (default: 4000)
- `STRIPE_SECRET_KEY`: Your Stripe secret key for payment processing

### 4. Start MongoDB
Make sure MongoDB service is running:
```bash
# On Windows
net start MongoDB

# On Mac/Linux
sudo systemctl start mongod
```

### 5. Run the Server
```bash
npm run server
```

The server will start on http://localhost:4000

## API Endpoints

### User Routes
- `POST /api/user/register` - Register a new user
- `POST /api/user/login` - Login user

### Food Routes
- `POST /api/food/add` - Add new food item (with image upload)
- `GET /api/food/list` - Get all food items
- `POST /api/food/remove` - Remove a food item

### Cart Routes (Requires Authentication)
- `POST /api/cart/add` - Add item to cart
- `POST /api/cart/remove` - Remove item from cart
- `POST /api/cart/get` - Get user's cart

### Order Routes
- `POST /api/order/place` - Place a new order (Requires Authentication)
- `POST /api/order/verify` - Verify payment
- `POST /api/order/userorders` - Get user's orders (Requires Authentication)
- `GET /api/order/list` - Get all orders (Admin)
- `POST /api/order/status` - Update order status (Admin)

## Project Structure
```
Backened/
├── config/
│   └── db.js              # Database connection
├── controller/
│   ├── userController.js  # User authentication logic
│   ├── foodController.js  # Food items management
│   ├── cartController.js  # Shopping cart logic
│   └── orderController.js # Order processing
├── middleware/
│   └── auth.js            # JWT authentication middleware
├── module/
│   ├── userModel.js       # User schema
│   ├── foodModel.js       # Food schema
│   └── orderModel.js      # Order schema
├── routes/
│   ├── userRoute.js       # User routes
│   ├── foodRoute.js       # Food routes
│   ├── cartRoute.js       # Cart routes
│   └── orderRoute.js      # Order routes
├── uploads/               # Uploaded images
├── .env                   # Environment variables
├── server.js              # Main server file
└── package.json           # Dependencies
```

## Notes
- Make sure to create the `uploads` folder if it doesn't exist
- Update the Stripe secret key in `.env` for payment functionality
- The frontend URL is set to `http://localhost:5173` in the order controller
