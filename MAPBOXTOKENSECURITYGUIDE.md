# 🔒 MAPBOX TOKEN SECURITY GUIDE

## The Short Answer

**For HTML files like yours: You DON'T need a .env file!**

Here's why:
- Your token is a PUBLIC token (starts with `pk.`)
- Public tokens are DESIGNED to be visible in browser code
- Mapbox protects them with URL restrictions instead

---

## 🔑 Two Types of Mapbox Tokens

### Public Token (pk.*)
```
pk.eyJ1IjoiZXhhbXBsZXMiLCJhIjoiY2p0MG01MXRqMW45cjQzb2R6b2ptc3J4MSJ9
```
- ✅ Safe to put in HTML/JavaScript
- ✅ Visible to users (that's OK!)
- ✅ Protected by URL restrictions
- ✅ What you should use

### Secret Token (sk.*)
```
sk.eyJ1IjoiZXhhbXBsZXMiLCJhIjoiY2p0MG01MXRqMW45cjQzb2R6b2ptc3J4MSJ9
```
- ❌ NEVER put in browser code
- ❌ Only use on servers
- ❌ Can do administrative things
- ❌ Not for your HTML file

---

## 🛡️ How to Secure Your Public Token

### Step 1: Add URL Restrictions

1. Go to: https://account.mapbox.com/
2. Click on your token
3. Find "URL restrictions" section
4. Add allowed URLs:

```
Examples of what to add:

If testing locally:
file://*
localhost:*

If on a website:
https://yourwebsite.com/*
https://www.yourwebsite.com/*

If on GitHub Pages:
https://yourusername.github.io/*
```

### Step 2: Set Token Scopes

Make sure your token only has these scopes:
- ✅ styles:read
- ✅ fonts:read
- ✅ datasets:read
- ✅ Vision (optional)

DON'T enable:
- ❌ styles:write
- ❌ datasets:write
- ❌ tokens:write

---

## 🤔 Why .env Doesn't Work Here

### What is a .env file?

A `.env` file hides secrets on a **SERVER**. Example:

```
# .env file
MAPBOX_TOKEN=pk.your-secret-token
```

### Why it won't work for your HTML file:

1. **No Server** - Your HTML file runs directly in the browser
2. **No Build Process** - You're opening the file directly, not compiling it
3. **Browser Can't Read .env** - Browsers can't access files on your computer
4. **.env needs Node.js/Python** - Requires a backend server to work

---

## 🌐 When DO You Need .env?

You'd need .env if you had:

### Server-Side Setup (Advanced):
```
Your Computer → Server (hides token) → Mapbox
```

This requires:
- Node.js or Python backend
- Server hosting (like Heroku, AWS)
- Build process
- More complex setup

### Your Current Setup (Simple):
```
Your Computer → Browser → Mapbox
             (token visible, but protected by URLs)
```

This is:
- ✅ Simpler
- ✅ No server needed
- ✅ Perfectly secure when configured right
- ✅ What most map websites use

---

## 📊 Real-World Examples

### Sites That Show Public Tokens (It's Normal!):

Open the browser console (F12) on these sites:
- Uber's website (uses Mapbox)
- Airbnb's maps
- The New York Times maps
- Foursquare

**They ALL show their public tokens in the code!**

Why? Because public tokens are DESIGNED for this.

---

## ✅ Your Security Checklist

For your HTML map, do these things:

### 1. Use a Public Token
- [ ] Token starts with `pk.`
- [ ] NOT a secret token (`sk.`)

### 2. Restrict URLs
- [ ] Go to Mapbox account
- [ ] Add URL restrictions
- [ ] Only allow your domains

### 3. Limit Token Scopes
- [ ] Only enable reading permissions
- [ ] Disable write permissions

### 4. Monitor Usage
- [ ] Check Mapbox dashboard monthly
- [ ] Watch for unusual activity
- [ ] Stay under free tier limits

### 5. Rotate if Needed
- [ ] Create new token if compromised
- [ ] Delete old token
- [ ] Update HTML file

---

## 🚨 What If Someone Steals My Token?

### If They Steal Your PUBLIC Token:

**They CAN:**
- Use your map views
- Potentially use up your free quota
- Use it only on URLs you allowed

**They CANNOT:**
- Delete your maps
- Modify your account
- Access your personal info
- Use it on other domains (if restricted)

### If They Steal Your SECRET Token:
**They CAN:**
- Do everything (bad!)
- This is why you NEVER put secret tokens in HTML

---

## 🔐 Maximum Security Setup

If you want MAXIMUM security, here's what pros do:

### 1. Restrict by URL
```
Only allow:
https://myrealestate.com/*
```

### 2. Create Token Per Project
```
Token 1: Main Website
Token 2: Demo Site
Token 3: Development
```

### 3. Monitor Dashboard
```
Weekly check:
- API calls used
- Where calls came from
- Any suspicious activity
```

### 4. Set Usage Limits
```
In Mapbox dashboard:
- Set maximum monthly API calls
- Get alerts at 80% usage
```

---

## 💡 For Your Specific Use Case

### If Putting on Your Personal Website:
```
1. Add URL restriction: https://yoursite.com/*
2. Use public token in HTML
3. Check usage monthly
```

### If Sharing Demo with Clients:
```
1. Add URL restriction: file://*
2. Share the HTML file
3. They can open it locally
```

### If Going Live for Business:
```
1. Buy Mapbox plan (not free tier)
2. Add multiple URL restrictions
3. Monitor dashboard weekly
4. Consider paid plan for support
```

---

## 🎓 Advanced: If You REALLY Want .env

If you want to hide the token completely, you'd need this setup:

### Backend Server Approach (Advanced - Not Recommended for You)

**1. Create a server (Node.js example):**
```javascript
// server.js
require('dotenv').config();
const express = require('express');
const app = express();

app.get('/api/map-token', (req, res) => {
    res.json({ token: process.env.MAPBOX_TOKEN });
});

app.listen(3000);
```

**2. Create .env file:**
```
MAPBOX_TOKEN=pk.your-token-here
```

**3. Update HTML to fetch from server:**
```javascript
// Instead of hardcoded token
fetch('/api/map-token')
    .then(r => r.json())
    .then(data => {
        mapboxgl.accessToken = data.token;
        // Initialize map
    });
```

**Why NOT to do this:**
- Requires server hosting ($$$)
- More complex
- Still exposes token to browser anyway
- Not worth it for public tokens

---

## 📋 Quick Decision Guide

### Use Current Setup (Token in HTML) If:
- ✅ Personal website
- ✅ Small business site
- ✅ Portfolio project
- ✅ Under 50,000 views/month
- ✅ No coding experience

### Use Server Setup (.env) If:
- ⚠️ Handling sensitive data
- ⚠️ Using secret tokens
- ⚠️ Large enterprise site
- ⚠️ Multiple API integrations
- ⚠️ Have developer team

**For your real estate map: Current setup is perfect!**

---

## 🎯 Summary

### What You Should Do:

1. ✅ Use public token (pk.*) in your HTML - **THIS IS FINE!**
2. ✅ Add URL restrictions in Mapbox dashboard
3. ✅ Monitor usage occasionally
4. ✅ Keep your token visible in the HTML file

### What You Should NOT Do:

1. ❌ Worry about .env files
2. ❌ Use secret tokens (sk.*)
3. ❌ Set up a backend server
4. ❌ Make it more complex than needed

---

## 🌟 The Bottom Line

**Your current setup is secure and professional!**

- Public tokens in browser code = Normal and expected
- Millions of websites do this
- URL restrictions = Your main security
- .env = Only for server-side code

**You're doing it right! Don't overcomplicate it.** 🎉

---

## 📞 Resources

- **Mapbox Security:** https://docs.mapbox.com/help/troubleshooting/how-to-use-mapbox-securely/
- **Token Management:** https://docs.mapbox.com/accounts/guides/tokens/
- **Access Control:** https://docs.mapbox.com/accounts/guides/tokens/#token-access-control

---

**Last Updated: November 2025**