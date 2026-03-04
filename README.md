# 🍔 Food Delivery Website - Full Stack Project

Complete food delivery website with Frontend, Backend, and Admin Panel.

## 📁 Project Structure

```
foodwebsite/
├── Backened/          # Node.js + Express + MongoDB Backend
├── fontened/          # React Frontend (Customer App)
└── admin/             # React Admin Panel
```

## 🚀 Quick Start Guide

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (installed and running)
- npm or yarn

### 1. Setup Backend

```bash
cd Backened
npm install
```

**Configure Environment Variables:**
Edit `Backened/.env` file:
```env
JWT_SECRET=random#secret
MONGODB_URI=mongodb://localhost:27017/food-delivery
PORT=4000
STRIPE_SECRET_KEY=your_stripe_secret_key_here
```

**Start MongoDB:**
```bash
# Windows
net start MongoDB

# Mac/Linux
sudo systemctl start mongod
```

**Run Backend Server:**
```bash
npm run server
```
Backend runs on: **http://localhost:4000**

### 2. Setup Frontend (Customer App)

```bash
cd fontened/foodwebsite
npm install
npm run dev
```
Frontend runs on: **http://localhost:5173**

### 3. Setup Admin Panel

```bash
cd admin
npm install
npm run dev
```
Admin Panel runs on: **http://localhost:5174**

## 🎯 Features

### Frontend (Customer App)
- ✅ Browse food items by category
- ✅ Add items to cart
- ✅ User authentication (Sign up/Login)
- ✅ Place orders with Stripe payment integration
- ✅ View order history
- ✅ Track order status
- ✅ Responsive design

### Admin Panel
- ✅ Add new food items with image upload
- ✅ View all food items
- ✅ Remove food items
- ✅ View all orders
- ✅ Update order status (Food Processing → Out for delivery → Delivered)

### Backend API
- ✅ User authentication with JWT
- ✅ Food items CRUD operations
- ✅ Shopping cart management
- ✅ Order processing
- ✅ Stripe payment integration
- ✅ Image upload handling

## 📡 API Endpoints

### User Routes
- `POST /api/user/register` - Register new user
- `POST /api/user/login` - Login user

### Food Routes
- `POST /api/food/add` - Add food item (with image)
- `GET /api/food/list` - Get all food items
- `POST /api/food/remove` - Remove food item

### Cart Routes (Requires Authentication)
- `POST /api/cart/add` - Add item to cart
- `POST /api/cart/remove` - Remove item from cart
- `POST /api/cart/get` - Get user's cart

### Order Routes
- `POST /api/order/place` - Place order (Requires Auth)
- `POST /api/order/verify` - Verify payment
- `POST /api/order/userorders` - Get user orders (Requires Auth)
- `GET /api/order/list` - Get all orders (Admin)
- `POST /api/order/status` - Update order status (Admin)

## 🛠️ Tech Stack

### Frontend & Admin
- React 18+
- React Router DOM
- Axios
- Vite

### Backend
- Node.js
- Express.js
- MongoDB + Mongoose
- JWT Authentication
- Bcrypt
- Multer (File uploads)
- Stripe (Payments)

## 📸 Screenshots Workflow

1. **Customer visits website** (Frontend - Port 5173)
   - Browse food items
   - Sign up / Login
   - Add items to cart
   - Place order and pay via Stripe

2. **Admin manages orders** (Admin Panel - Port 5174)
   - Add new food items
   - View all orders
   - Update order status

3. **Backend handles all requests** (Port 4000)
   - Authentication
   - Database operations
   - Payment processing

## 🔐 Authentication Flow

1. User signs up/logs in via Frontend
2. Backend generates JWT token
3. Token stored in localStorage
4. Token sent with each authenticated request
5. Backend verifies token before processing

## 💳 Payment Flow

1. User places order with delivery details
2. Backend creates Stripe checkout session
3. User redirected to Stripe payment page
4. After payment, redirected to verify page
5. Order status updated in database
6. User can view order in My Orders

## 📝 Important Notes

- Make sure MongoDB is running before starting the backend
- Update Stripe secret key in `.env` for payment functionality
- The `uploads` folder in backend stores food item images
- Admin panel and frontend both connect to the same backend

## 🐛 Troubleshooting

**Backend won't start:**
- Check if MongoDB is running
- Verify .env file configuration
- Check if port 4000 is available

**Frontend can't fetch data:**
- Ensure backend is running on port 4000
- Check browser console for CORS errors
- Verify API URLs in code

**Images not loading:**
- Check if uploads folder exists in backend
- Verify image upload in admin panel works
- Check network tab for image URL

## 📚 Folder Details

### Backend Structure
```
Backened/
├── config/
│   └── db.js              # Database connection
├── controller/
│   ├── userController.js  # User auth logic
│   ├── foodController.js  # Food management
│   ├── cartController.js  # Cart logic
│   └── orderController.js # Order processing
├── middleware/
│   └── auth.js            # JWT middleware
├── module/
│   ├── userModel.js       # User schema
│   ├── foodModel.js       # Food schema
│   └── orderModel.js      # Order schema
├── routes/
│   ├── userRoute.js
│   ├── foodRoute.js
│   ├── cartRoute.js
│   └── orderRoute.js
├── uploads/               # Food item images
└── server.js              # Main server file
```

## 🎓 Learning Resources

This project demonstrates:
- Full-stack MERN development
- JWT authentication
- File upload handling
- Payment gateway integration
- RESTful API design
- React Router
- State management with Context API

## 📄 License

This project is for educational purposes.

## 👨‍💻 Development

To contribute or modify:
1. Make changes in respective folders
2. Test thoroughly
3. Update documentation if needed

---

**Happy Coding! 🚀**
