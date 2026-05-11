# How to Run Admin Panel Locally

## ⚠️ IMPORTANT: Don't Open Directly from File Explorer!

If you're seeing "Failed to fetch" error, it's because you're opening the admin panel from `file://` URL which blocks API requests for security.

## ✅ Solution: Run on Local Server

### Option 1: Using npm (Recommended)

1. **Open terminal in admin folder:**
   ```
   cd "C:\Users\Bryan\Documents\WEKA SOKO\weka-soko-admin"
   ```

2. **Install dependencies (first time only):**
   ```
   npm install
   ```

3. **Start the development server:**
   ```
   npm start
   ```

4. **Open browser and go to:**
   ```
   http://localhost:3000
   ```

5. **Login with:**
   - Email: `admin@wekasoko.co.ke`
   - Password: `WekaSoko@Admin2026`

### Option 2: Use Vercel Deployment (Production)

If you have Vercel CLI installed:
```
npm install -g vercel
vercel --prod
```

Then access from your deployed URL like:
```
https://weka-soko-admin.vercel.app
```

## 🔍 Why "Failed to fetch" Happens

When you open `index.html` directly from your file system:
- Browser uses `file://` protocol
- Security blocks API requests to `https://` URLs
- Result: "Failed to fetch" error

When you run on `http://localhost:3000`:
- Browser uses `http://` protocol
- API requests work normally
- Login works! ✅

## 🎯 Quick Test

After running `npm start`, open:
1. http://localhost:3000
2. Login with admin credentials above
3. Should work perfectly!

## Current Status

✅ **Backend:** Working (https://weka-soko-backend.onrender.com)
✅ **Admin Credentials:** Valid and tested
✅ **Password Toggle:** Now has show/hide SVG icons
✅ **API URL:** Correctly configured to Render

Only issue was running from file:// instead of localhost!
