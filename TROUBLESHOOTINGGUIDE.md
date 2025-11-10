# TROUBLESHOOTING GUIDE 🔧

## Common Issues & Solutions

---

## 🚫 Issue: Map Shows "Please use your own token"

### Problem:
You're using the demo Mapbox token that has limited access.

### Solution:
1. Go to https://account.mapbox.com/
2. Sign up for a FREE account
3. Copy your access token
4. Open `3d-soaring-map.html` in a text editor
5. Find line 191:
   ```javascript
   mapboxgl.accessToken = 'pk.eyJ1IjoiZXhhbXBsZXMi...'
   ```
6. Replace everything between the quotes with YOUR token
7. Save the file
8. Refresh your browser

---

## 🚫 Issue: Map Won't Load / Blank Page

### Possible Causes & Solutions:

**1. No Internet Connection**
- The map requires internet to load
- Check your connection
- Try refreshing the page

**2. Browser Blocking Scripts**
- Check if browser shows a "blocked content" message
- Click "Allow" or "Unblock" if prompted

**3. Opening from Wrong Location**
- Make sure you're opening the file from your computer
- Don't try to open it from email or compressed folder

**4. Check Browser Console:**
- Press F12 to open developer tools
- Click "Console" tab
- Look for error messages
- Most common: "Invalid access token"

---

## 🚫 Issue: Pins Don't Appear

### Solution Checklist:

**Check Coordinate Format:**
```javascript
// ✅ CORRECT
coordinates: [-118.2437, 34.0522]

// ❌ WRONG - Missing negative sign
coordinates: [118.2437, 34.0522]

// ❌ WRONG - Backwards (lat, long)
coordinates: [34.0522, -118.2437]
```

**Remember:**
- Format is [longitude, latitude]
- Longitude comes FIRST
- In USA, longitude is negative (west)
- Check for typos in numbers

**Verify Commas:**
```javascript
// ✅ CORRECT
{
    coordinates: [-118.2437, 34.0522],
    name: "Property 1",
    price: "$1,000,000",
},  // ← Comma here!
{
    coordinates: [-122.4194, 37.7749],
    name: "Property 2",
```

---

## 🚫 Issue: Info Card Won't Show

### Solutions:

**1. Hover Directly on Pin**
- Make sure cursor is touching the colored marker
- The pin is the colorful teardrop shape

**2. Move Slowly**
- Sometimes moving too fast misses the hover
- Hover and pause for a second

**3. Check Z-Index**
- Another element might be blocking
- Press F12 and check console for errors

---

## 🚫 Issue: Map is Laggy/Slow

### Performance Solutions:

**1. Reduce Number of Properties**
```javascript
// Start with just 3-5 properties
// Add more gradually
```

**2. Use Simpler Map Style**
```javascript
// Instead of satellite:
style: 'mapbox://styles/mapbox/satellite-streets-v12',

// Try streets:
style: 'mapbox://styles/mapbox/streets-v12',
```

**3. Reduce 3D Effects**
Find line 318 and change:
```javascript
'exaggeration': 1.5  // Change to 1.0 or 0.5
```

**4. Update Your Browser**
- Make sure you're using latest Chrome, Firefox, or Edge

---

## 🚫 Issue: Syntax Error Messages

### Common JavaScript Errors:

**Missing Comma**
```javascript
// ❌ ERROR - Missing comma after first property
{
    name: "Property 1",
    price: "$1M"
}  // ← Need comma here!
{
    name: "Property 2"
```

**Extra Comma**
```javascript
// ❌ ERROR - Comma after last property
{
    name: "Last Property",
    price: "$1M"
},  // ← Remove this comma!
];  // Array ends here
```

**Missing Quote**
```javascript
// ❌ ERROR
name: "Property Name,  // ← Missing closing quote

// ✅ CORRECT
name: "Property Name",
```

**Missing Bracket**
```javascript
// ❌ ERROR - Missing closing brace
{
    name: "Property",
    price: "$1M"
// ← Need } here

// ✅ CORRECT
{
    name: "Property",
    price: "$1M"
}
```

---

## 🚫 Issue: Camera Won't Tilt

### Solutions:

**1. Zoom In More**
- Camera only tilts when zoom > 5
- Try zooming in further

**2. Check Pitch Setting**
Find line 352:
```javascript
// Make sure this line exists and isn't commented out:
targetPitch = Math.min((zoom - 5) * 8, 60);
```

**3. Check Browser Support**
- 3D features require WebGL
- Update your browser if very old

---

## 🚫 Issue: Cursor Not Showing

### Solutions:

**1. Mouse Not Moving**
- The custom cursor appears when you move your mouse
- Try moving the mouse

**2. Cursor Hidden by Accident**
Find line 20 and make sure it says:
```javascript
cursor: none;  // This hides default cursor to show custom one
```

**3. Custom Cursor CSS Missing**
Check that lines 22-45 exist (the #custom-cursor section)

---

## 🚫 Issue: Can't Find Where to Edit

### Quick Reference:

| What You Want to Change | Search For This |
|------------------------|-----------------|
| Mapbox Token | `mapboxgl.accessToken` |
| Properties List | `const properties = [` |
| Map Center | `center: [` |
| Starting Zoom | `zoom:` (line 197) |
| Map Style | `style: 'mapbox://` |
| Pin Colors | `background: linear-gradient` (line 218) |
| Info Card Colors | `background: linear-gradient` (line 77) |

### How to Search in Text Editor:
- **Windows:** Ctrl + F
- **Mac:** Cmd + F

---

## 🚫 Issue: File Won't Save

### Solutions:

**1. File is Read-Only**
- Right-click file → Properties
- Uncheck "Read-only"
- Click OK

**2. File is Open in Browser**
- Close browser first
- Then edit and save
- Reopen in browser

**3. No Permission to Save**
- Save to Desktop or Documents folder
- Avoid saving to system folders

---

## 🚫 Issue: Changes Don't Show Up

### Solutions:

**1. Hard Refresh Browser**
- **Windows:** Ctrl + Shift + R
- **Mac:** Cmd + Shift + R
- Or: Ctrl + F5

**2. Clear Browser Cache**
- Chrome: Settings → Privacy → Clear browsing data
- Firefox: Settings → Privacy → Clear Data
- Safari: Develop → Empty Caches

**3. Make Sure File Saved**
- Check file's "Date Modified"
- Should be recent

---

## 🚫 Issue: Coordinates Wrong

### How to Get Correct Coordinates:

**Method 1: Google Maps**
1. Go to maps.google.com
2. Find your location
3. Right-click on exact spot
4. Click coordinates at top (they'll copy)
5. Format: First number is longitude, second is latitude

**Method 2: LatLong.net**
1. Go to https://www.latlong.net/
2. Search address
3. Copy decimal coordinates
4. Longitude is listed first

**Method 3: Google Search**
1. Google: "coordinates of [address]"
2. Results show lat, long
3. Reverse them to long, lat for the code

**Example:**
- Google shows: `34.0522° N, 118.2437° W`
- In code use: `[-118.2437, 34.0522]`
- (Note the negative sign for West!)

---

## 🚫 Issue: File Too Large / Won't Open

### Solutions:

**If You Have Many Properties:**
1. Start a new file
2. Copy code in sections
3. Test after each section

**If Browser Crashes:**
1. Try different browser
2. Close other tabs/programs
3. Restart computer

---

## 🧪 Testing Your Changes

### Step-by-Step Testing:

1. **Make ONE change at a time**
2. **Save the file**
3. **Refresh browser** (Ctrl+Shift+R)
4. **Check if it works**
5. If broken, undo that change
6. If works, make next change

---

## 📱 Browser-Specific Issues

### Chrome
- Best compatibility
- If issues: Update Chrome
- Check: chrome://version/

### Firefox
- Usually works well
- Enable WebGL in settings if needed

### Safari
- May need to enable developer features
- Safari → Preferences → Advanced → Show Develop menu

### Edge
- Update to latest version
- Works same as Chrome

### Internet Explorer
- ❌ NOT SUPPORTED
- Please use Chrome, Firefox, Edge, or Safari

---

## 🆘 Still Having Issues?

### Diagnostic Steps:

1. **Open Browser Console** (F12)
2. **Look for red error messages**
3. **Take screenshot of error**
4. **Note which line number** is mentioned

### Common Error Messages:

| Error Message | What It Means | Solution |
|---------------|---------------|----------|
| "Invalid token" | Wrong Mapbox token | Get new token from Mapbox |
| "Unexpected token" | JavaScript syntax error | Check for missing commas/quotes |
| "Cannot read property" | Variable is undefined | Check property names |
| "Failed to fetch" | Network/URL issue | Check internet connection |

---

## ✅ Everything Working? Great!

If you got it working, here are next steps:
1. Add your real properties
2. Try different map styles
3. Customize colors
4. Add more locations

---

## 🔄 Starting Over

If everything is broken and you want to start fresh:
1. Download the original files again
2. Start with the original code
3. Make changes slowly
4. Test after each change

---

**Remember: Small changes, test often, save frequently!**