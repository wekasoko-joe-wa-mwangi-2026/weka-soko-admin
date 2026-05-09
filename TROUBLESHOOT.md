# Admin Login Troubleshooting Guide

## Problem: "Failed to Fetch" Error

### What I've Done
- ✅ Added detailed error logging to track the exact issue
- ✅ Backend is working perfectly (tested and confirmed)
- ✅ Admin credentials are valid

### How to Debug

**Step 1: Open Browser Console**
1. Open your admin panel
2. Press **F12** (or right-click → Inspect)
3. Click the **Console** tab
4. Try to login again
5. Look for error messages in RED

**Step 2: Check the Console Output**
You should see:
```
API Base URL: https://weka-soko-backend.onrender.com
Request: POST https://weka-soko-backend.onrender.com/api/auth/admin-login
```

**If you see "Network error":**
- Backend is unreachable
- Check your internet connection
- Check if backend is running: https://weka-soko-backend.onrender.com/health

**If you see "CORS" error:**
- Backend CORS settings need adjustment
- This is a server configuration issue

**If you see "Mixed Content" error:**
- You're accessing admin panel via HTTP but backend is HTTPS
- Must use HTTPS for both

### Current Status

**Backend:** ✅ Working
- URL: https://weka-soko-backend.onrender.com
- Health: https://weka-soko-backend.onrender.com/health (returns 200)
- Login endpoint: Working
- Admin user exists: admin@wekasoko.co.ke

**Frontend:** ✅ Updated with logging
- Commit: 9471e40d
- Has detailed console logging
- Shows exact API URL being used

### Next Steps

1. **Deploy the latest frontend** (if on Vercel/Netlify)
   - Go to your deployment platform
   - Trigger redeploy
   - Wait 1-2 minutes

2. **Open browser console (F12)**
   - Try to login
   - Copy the EXACT error message
   - Share it with me

3. **Common fixes:**
   - If CORS error: Backend needs CORS update
   - If Mixed Content: Use HTTPS for admin panel
   - If Network Error: Backend might be sleeping on Render

### Render Backend Status

The backend is on Render FREE tier which:
- Sleeps after 15 minutes of inactivity
- Takes 30-60 seconds to wake up
- To wake it up: Visit https://weka-soko-backend.onrender.com/health

**OR** upgrade to Render Starter ($7/month) to prevent sleep.

### Test Login Now

1. Wake up backend: Visit https://weka-soko-backend.onrender.com/health
2. Wait 30 seconds
3. Go to admin panel
4. Open F12 Console
5. Try login with:
   - Email: `admin@wekasoko.co.ke`
   - Password: `WekaSoko@Admin2026`
6. Check console for exact error

Share the console error message and I'll fix it immediately!
