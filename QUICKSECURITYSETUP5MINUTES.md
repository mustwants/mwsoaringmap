# 🛡️ QUICK SECURITY SETUP - 5 MINUTES

## The Real Protection: URL Restrictions

Instead of .env files, secure your token by telling Mapbox "only work on MY websites"

---

## 📋 Step-by-Step Instructions

### Step 1: Go to Your Mapbox Account
```
1. Open browser
2. Go to: https://account.mapbox.com/
3. Log in
```

### Step 2: Find Your Token
```
1. Look for "Access tokens" section
2. Find your token (the one you're using)
3. Click on it
```

### Step 3: Add URL Restrictions
```
1. Scroll to "URL restrictions" section
2. Click "Add URL restriction"
3. Enter your URLs (see examples below)
4. Click "Save"
```

---

## 🌐 What URLs Should You Add?

### If Testing on Your Computer:
```
Add this:
file://*

This allows the file to work when you open it locally
```

### If Putting on a Website:
```
Add these:
https://yourwebsite.com/*
https://www.yourwebsite.com/*

Replace "yourwebsite.com" with your actual domain
```

### If Using Both:
```
Add all of them:
file://*
https://yourwebsite.com/*
https://www.yourwebsite.com/*
```

### If On a Subdomain:
```
Add this:
https://maps.yourwebsite.com/*
```

---

## ✅ What This Does

### With URL Restrictions:
- ✅ Token works on YOUR sites only
- ✅ Token works on YOUR computer only
- ✅ Won't work if someone copies it
- ✅ You're protected!

### Without URL Restrictions:
- ⚠️ Token works on ANY website
- ⚠️ Anyone can use your map views
- ⚠️ Could use up your free quota
- ⚠️ Not ideal

---

## 🎯 Example Setup

### For Real Estate Agent Website:

**Your situation:**
- Website: https://johnsmithhomes.com
- Testing locally first

**Your URL restrictions:**
```
file://*
https://johnsmithhomes.com/*
https://www.johnsmithhomes.com/*
```

**Result:**
- Works on your computer ✅
- Works on your website ✅
- Won't work anywhere else ✅

---

## 🔍 How to Check It's Working

### Test 1: On Your Computer
```
1. Open your HTML file
2. Map should load normally
3. ✅ If it works, URL restrictions are correct!
```

### Test 2: Remove Restriction Temporarily
```
1. In Mapbox, remove all URL restrictions
2. Refresh your map
3. Should still work
4. Add restrictions back
5. Refresh again
6. Should still work
```

---

## 🚨 Common Mistakes

### ❌ Wrong: Missing the asterisk
```
https://mywebsite.com
```
**Problem:** Only works on homepage

### ✅ Correct: Include the asterisk
```
https://mywebsite.com/*
```
**Result:** Works on all pages!

### ❌ Wrong: Including http instead of https
```
http://mywebsite.com/*
```
**Problem:** Modern sites use https

### ✅ Correct: Use https
```
https://mywebsite.com/*
```

---

## 📊 Visual Checklist

After setting up URL restrictions, you should have:

```
✅ Token Type: Public (pk.*)
✅ URL Restrictions: Added
✅ Token Scopes: Only read permissions
✅ Map Status: Working on allowed URLs
```

---

## 💡 Pro Tips

### Tip 1: Start Broad, Then Narrow
```
Week 1: Allow file://* (testing)
Week 2: Add your domain (going live)
Week 3: Remove file://* (production only)
```

### Tip 2: Multiple Environments
```
Development token: file://*
Production token: https://yoursite.com/*
```

### Tip 3: Check Monthly
```
Set calendar reminder to:
- Check Mapbox dashboard
- Review API usage
- Verify restrictions still correct
```

---

## 🎓 Understanding the Protection

### Think of it Like a House Key:

**Without URL Restrictions:**
- Key works in ANY door
- Anyone can use it anywhere
- Not secure!

**With URL Restrictions:**
- Key only works in YOUR doors
- Useless to anyone else
- Secure! 🔒

### Your Token:

**Without URL Restrictions:**
- Token works on any website
- Anyone can copy and use it
- Uses YOUR quota

**With URL Restrictions:**
- Token only works on YOUR sites
- Copying it is useless
- Protected! 🛡️

---

## ⚡ Quick Setup (Copy This)

```
1. Go to: https://account.mapbox.com/
2. Click your token
3. Scroll to "URL restrictions"
4. Add: file://*
5. Add: https://your-site.com/*
6. Click Save
7. Done! ✅
```

---

## 🔄 What If You Need to Change URLs Later?

### Easy! Just:
```
1. Go back to Mapbox account
2. Click your token
3. Edit URL restrictions
4. Add/remove as needed
5. Save
6. Refresh your map
```

**Changes are instant!** No need to update your HTML file.

---

## 📱 Mobile/Responsive Note

URL restrictions work for:
- ✅ Desktop browsers
- ✅ Mobile browsers
- ✅ Tablets
- ✅ Any device

Same restrictions apply to all devices automatically!

---

## 🎉 You're Secure!

Once you've added URL restrictions:
- Your token is protected
- Only YOUR sites can use it
- No .env files needed
- Professional setup!

---

## 🆘 Troubleshooting URL Restrictions

### Map Won't Load After Adding Restrictions:

**Problem:** Too restrictive
**Solution:** 
```
1. Double-check your URLs
2. Make sure they match exactly
3. Include the /* at the end
4. Try adding file://* if testing locally
```

### Works on Computer But Not Website:

**Problem:** Missing domain restriction
**Solution:**
```
1. Add your actual website domain
2. Include both www and non-www versions:
   https://website.com/*
   https://www.website.com/*
```

---

## 📞 Final Reminder

**YOU DON'T NEED .env FILES!**

Instead, you just need:
1. ✅ Public token (pk.*)
2. ✅ URL restrictions
3. ✅ That's it!

This is how professional websites do it. You're all set! 🚀

---

**Setup Time: 5 minutes**
**Security Level: Professional**
**Complexity: Simple**
**Cost: Free**

**Perfect!** ✨