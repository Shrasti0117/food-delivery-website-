# Payment Configuration

## Development Mode (No Stripe Required)

The application is currently configured to work **without Stripe** for development and testing. Orders will be processed without actual payment.

To enable development mode, ensure `.env` has:
```
DEVELOPMENT_MODE=true
```

## Production Mode (With Stripe)

To enable real Stripe payments:

### Step 1: Get Stripe API Keys
1. Go to [https://stripe.com](https://stripe.com)
2. Create a free account
3. Navigate to **Developers** → **API Keys**
4. Copy your **Secret Key** (starts with `sk_test_` for test mode)

### Step 2: Update .env
```env
STRIPE_SECRET_KEY=sk_test_your_actual_stripe_key_here
DEVELOPMENT_MODE=false
```

### Step 3: Restart Backend
```bash
cd Backened
npm run server
```

## How It Works

### Development Mode
- Orders are created in database
- Payment verification is automatic
- No actual payment processing
- Perfect for testing the app

### Production Mode (Stripe)
- Redirects to Stripe checkout
- Real payment processing
- Secure payment handling
- Production-ready

---

**Current Mode:** Development (No Stripe needed) ✅
