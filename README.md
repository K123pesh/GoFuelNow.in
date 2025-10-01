# 🚀 Fuel Delivery App - Premium Fuel Delivery Service

A modern, full-featured fuel delivery application built with React, TypeScript, and Supabase.

## 🎯 Features

### Customer Features
- 📱 Phone OTP verification
- 📍 GPS location & saved addresses
- ⛽ Multiple fuel types (Petrol, Diesel, CNG, Premium)
- 🗺️ State-wise fuel pricing (10+ Indian states)
- 💳 6 payment methods (Wallet, UPI, QR, Card, Net Banking, COD)
- 🎟️ Promo code system with discounts
- 📋 Order history & tracking
- ⭐ Reviews & ratings
- 💰 Wallet management
- 🎁 Referral program with rewards
- 🏆 Loyalty points & tier system (Silver, Gold, Platinum)
- 🔔 Notifications system

### Admin Features
- 📊 Business analytics dashboard
- 📦 Order management
- 🔄 Order status updates
- 👥 Customer management
- 💵 Revenue tracking

## 🛠️ Technologies Used

- **Frontend:** React 18, TypeScript
- **Build Tool:** Vite
- **UI Framework:** Tailwind CSS
- **UI Components:** shadcn/ui, Radix UI
- **Backend:** Supabase (PostgreSQL)
- **Authentication:** Supabase Auth
- **State Management:** React Hooks
- **Icons:** Lucide React
- **Routing:** React Router DOM

## 📦 Installation

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn

### Setup Steps

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd fuel-buddy-fixed

# 2. Install dependencies
npm install

# 3. Set up environment variables
# Create .env file and add your Supabase credentials
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# 4. Run database migrations
npx supabase db push

# 5. Generate TypeScript types
npx supabase gen types typescript --local > src/integrations/supabase/types.ts

# 6. Start development server
npm run dev
```

## 🚀 Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run linter
npm run lint
```

## 📁 Project Structure

```
fuel-buddy-fixed/
├── src/
│   ├── components/        # React components
│   │   └── OrderFlow.tsx  # Main order flow component
│   ├── pages/            # Page components
│   │   ├── OrderHistory.tsx
│   │   ├── UserProfile.tsx
│   │   └── AdminDashboard.tsx
│   ├── services/         # API services
│   │   ├── orderService.ts
│   │   ├── userService.ts
│   │   └── promoCodeService.ts
│   ├── integrations/     # Third-party integrations
│   │   └── supabase/
│   └── main.tsx          # App entry point
├── supabase/
│   └── migrations/       # Database migrations
├── public/               # Static assets
└── package.json
```

## 🗄️ Database Schema

The app uses 9 main tables:
- `users` - User profiles with wallet & loyalty
- `saved_addresses` - Multiple delivery addresses
- `orders` - Complete order management
- `promo_codes` - Discount codes
- `promo_code_usage` - Usage tracking
- `referrals` - Referral program
- `wallet_transactions` - Payment history
- `order_status_history` - Status tracking
- `notifications` - User notifications

## 🎨 Pre-loaded Features

### Promo Codes
- **FIRST100** - ₹100 off on first order
- **SAVE20** - 20% off on orders above ₹1000
- **FUEL50** - Flat ₹50 off
- **WELCOME15** - 15% off for new users

### State-wise Pricing
Supports 10 major Indian states with real fuel prices

## 🚢 Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# Deploy dist/ folder to Netlify
```

### Other Platforms
Build the project and deploy the `dist/` folder to any static hosting service.

## 📝 Environment Variables

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

## 🔐 Security

- Row Level Security (RLS) enabled on all tables
- Secure authentication with Supabase
- Payment data encryption
- HTTPS support for production

## 📄 License

MIT License - Feel free to use this project for personal or commercial purposes.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For issues and questions, please open an issue on GitHub.

---

**Built with ❤️ using React, TypeScript, and Supabase**
