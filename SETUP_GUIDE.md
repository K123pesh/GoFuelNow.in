# 🚀 Quick Setup Guide

## Step-by-Step Setup Instructions

### 1️⃣ Run Database Migration

Open terminal in project folder and run:

```bash
# Start Supabase (if not already running)
npx supabase start

# Apply the database migration
npx supabase db push
```

This creates all tables, indexes, and loads sample promo codes.

---

### 2️⃣ Generate TypeScript Types

```bash
# Generate types from your database schema
npx supabase gen types typescript --local > src/integrations/supabase/types.ts
```

This fixes all TypeScript errors by creating proper types for new tables.

---

### 3️⃣ Update App Router

Open `src/App.tsx` or your router file and add these routes:

```typescript
import OrderHistory from './pages/OrderHistory';
import AdminDashboard from './pages/AdminDashboard';

// Add these routes
<Route path="/orders" element={<OrderHistory />} />
<Route path="/admin" element={<AdminDashboard />} />
```

---

### 4️⃣ Test the Features

#### Test Promo Codes:
1. Go to order flow
2. At payment step, try these codes:
   - `FIRST100` - ₹100 off
   - `SAVE20` - 20% off
   - `FUEL50` - ₹50 off
   - `WELCOME15` - 15% off

#### Test Order History:
1. Place an order
2. Navigate to `/orders`
3. See your order history

#### Test Admin Dashboard:
1. Navigate to `/admin`
2. View all orders
3. Update order status

---

### 5️⃣ Fix TypeScript Errors (If Any)

If you see TypeScript errors in services, it's because Supabase types need to be regenerated:

```bash
npx supabase gen types typescript --local > src/integrations/supabase/types.ts
```

Then restart your dev server:

```bash
npm run dev
```

---

## ✅ Verification Checklist

- [ ] Database migration ran successfully
- [ ] TypeScript types generated
- [ ] Routes added to router
- [ ] Dev server running without errors
- [ ] Can place orders
- [ ] Can apply promo codes
- [ ] Can view order history
- [ ] Admin dashboard accessible

---

## 🎯 What You Can Do Now

### As a Customer:
✅ Place fuel orders with state-wise pricing  
✅ Use current location or saved addresses  
✅ Apply promo codes for discounts  
✅ View order history  
✅ Rate and review delivered orders  
✅ Track order status  

### As an Admin:
✅ View business statistics  
✅ Manage all orders  
✅ Update order status  
✅ Filter orders by status  
✅ View customer details  

---

## 📊 Database Tables Created

✅ **users** - User profiles with wallet & loyalty points  
✅ **saved_addresses** - Multiple delivery addresses  
✅ **orders** - Complete order management  
✅ **promo_codes** - Discount codes (4 pre-loaded)  
✅ **promo_code_usage** - Track usage  
✅ **referrals** - Referral program  
✅ **wallet_transactions** - Payment history  
✅ **order_status_history** - Status tracking  
✅ **notifications** - User notifications  

---

## 🐛 Troubleshooting

### Issue: TypeScript errors in service files
**Solution:** Run `npx supabase gen types typescript --local`

### Issue: Tables not found
**Solution:** Run `npx supabase db push` to apply migration

### Issue: Promo codes not working
**Solution:** Check database - promo codes should be auto-loaded

### Issue: Orders not saving
**Solution:** Check Supabase connection and RLS policies

---

## 📝 Important Notes

1. **Mock User ID:** Currently using `'mock-user-id'` for testing
   - Replace with real auth user ID in production
   - Update in `OrderFlow.tsx` and `OrderHistory.tsx`

2. **Wallet Balance:** Default is ₹10,500
   - Can be updated in database
   - Deducted automatically on wallet payments

3. **Order Numbers:** Auto-generated format: `FB-YYYYMMDD-XXXX`

4. **RLS Enabled:** All tables have Row Level Security
   - Secure by default
   - Users can only see their own data

---

## 🎉 You're All Set!

Your fuel delivery app now has:
- ✅ Complete database backend
- ✅ Order management system
- ✅ Promo code functionality
- ✅ Admin dashboard
- ✅ Order history & reviews
- ✅ State-wise pricing
- ✅ Location features

**Ready for production after adding authentication!**

---

## 📞 Need Help?

Check these files for reference:
- `FEATURES_ADDED.md` - Complete feature documentation
- `supabase/migrations/20251001000000_create_fuel_delivery_schema.sql` - Database schema
- `src/services/orderService.ts` - Order management API
- `src/services/promoCodeService.ts` - Promo code API

Happy coding! 🚀
