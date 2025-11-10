# 3D SOARING MAP - SETUP CHECKLIST ✅

Print this page or keep it handy!

---

## 📋 STEP-BY-STEP SETUP

### □ STEP 1: Get Mapbox Token (5 minutes)
```
1. Open browser
2. Go to: https://account.mapbox.com/
3. Click "Sign Up" (FREE)
4. Verify email
5. Copy token (starts with pk.eyJ...)
6. Save token in a note for now
```

### □ STEP 2: Edit HTML File (2 minutes)
```
1. Right-click: 3d-soaring-map.html
2. Open with: Notepad (Windows) or TextEdit (Mac)
3. Press: Ctrl+F (Cmd+F on Mac)
4. Search for: mapboxgl.accessToken
5. Replace the token between quotes with YOUR token
6. Save file (Ctrl+S or Cmd+S)
7. Close editor
```

### □ STEP 3: Test It! (1 minute)
```
1. Double-click: 3d-soaring-map.html
2. Map should load in your browser
3. Try scrolling to zoom
4. Hover over pins to see info cards
```

---

## ✅ SUCCESS CHECKLIST

After opening the file, you should see:

- ✅ Map of United States loads
- ✅ 8 colored pins on major cities
- ✅ Custom cursor when you move mouse
- ✅ Instructions box in top-left
- ✅ Zoom indicator in bottom-right
- ✅ Can zoom in/out with mouse wheel
- ✅ Camera tilts when zooming in
- ✅ Info card appears when hovering on pins

---

## 🎯 QUICK CONTROLS

```
🖱️ MOUSE WHEEL = Zoom in/out
🖱️ MOVE MOUSE = Camera follows slightly
🖱️ HOVER ON PIN = Show property info
```

---

## 📍 YOUR FIRST CUSTOMIZATION

### Adding Your Own Property:

```javascript
1. Open file in text editor
2. Find: const properties = [
3. Scroll to last property
4. Add comma after last }
5. Copy this template:

{
    coordinates: [-XXX.XXXX, XX.XXXX],
    name: "Your Property Name",
    price: "$XXX,XXX",
    beds: X,
    baths: X,
    sqft: "X,XXX",
    agent: "Your Name",
    phone: "(XXX) XXX-XXXX",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}

6. Save file
7. Refresh browser (Ctrl + Shift + R)
```

---

## 🗺️ FIND COORDINATES

### Option 1: Google Maps
```
1. Go to maps.google.com
2. Search address
3. Right-click on location
4. Click coordinates at top
5. Copy them
6. Format: [longitude, latitude]
   (First number is longitude!)
```

### Option 2: LatLong.net
```
1. Go to: https://www.latlong.net/
2. Search address
3. Copy Decimal Degrees
4. Put in format: [longitude, latitude]
```

---

## 🎨 QUICK CUSTOMIZATIONS

### Change Map Style (Line 195)
```javascript
// Satellite (current)
style: 'mapbox://styles/mapbox/satellite-streets-v12'

// Streets
style: 'mapbox://styles/mapbox/streets-v12'

// Dark Mode
style: 'mapbox://styles/mapbox/dark-v11'
```

### Change Starting Location (Line 196-197)
```javascript
// Whole USA
center: [-98.5795, 39.8283], zoom: 4

// California
center: [-119.4179, 36.7783], zoom: 6

// Texas
center: [-99.9018, 31.9686], zoom: 6

// Florida
center: [-81.5158, 27.6648], zoom: 7
```

### Change Pin Color (Line 218)
```javascript
// Purple (current)
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

// Blue
background: linear-gradient(135deg, #4299e1 0%, #2c5282 100%);

// Green
background: linear-gradient(135deg, #48bb78 0%, #2f855a 100%);

// Orange
background: linear-gradient(135deg, #fc466b 0%, #f76b1c 100%);
```

---

## 🚨 TROUBLESHOOTING

### Map won't load?
```
→ Check: Did you add your Mapbox token?
→ Check: Is there internet connection?
→ Try: Hard refresh (Ctrl+Shift+R)
```

### Pins missing?
```
→ Check: Coordinates format [long, lat]
→ Check: Negative sign for longitude (in USA)
→ Check: Commas between properties
```

### Error messages?
```
→ Press: F12 to see console
→ Look: For red error messages
→ Common: Missing comma or quote
```

### Changes not showing?
```
→ Did you: Save the file?
→ Try: Hard refresh (Ctrl+Shift+R)
→ Try: Close and reopen browser
```

---

## 📚 DOCUMENTATION FILES

```
README.md              = Full detailed guide
QUICK-START.md         = 3-step quick start
CUSTOMIZATION-EXAMPLES = Copy-paste code examples
TROUBLESHOOTING.md     = Problem solutions
```

---

## 💾 BACKUP YOUR WORK

Before making big changes:
```
1. Make a copy of the HTML file
2. Name it: 3d-soaring-map-BACKUP.html
3. If you break something, use the backup!
```

---

## 🎓 LEARNING PATH

```
Week 1: Get it working with your token
Week 2: Add your first property
Week 3: Try different map styles
Week 4: Customize colors
Week 5: Add all your properties
```

---

## ✨ TIPS FOR SUCCESS

✅ Make ONE change at a time
✅ Test after EVERY change
✅ Save frequently
✅ Keep a backup copy
✅ Use Ctrl+F to find things
✅ Check for typos carefully
✅ Don't remove commas by accident

---

## 🎯 GOALS CHECKLIST

- □ Get map working with my token
- □ Add my first property
- □ Add 5 properties total
- □ Change map style
- □ Change colors to match my brand
- □ Adjust starting view
- □ Share with colleagues
- □ Put on my website

---

**You've got this! Take it one step at a time! 🚀**

---

## 📞 REMEMBER

- Mapbox FREE account = 50,000 map loads/month
- Perfect for personal sites and demos
- No credit card needed
- Keep your token private!

---

**Last Updated: November 2025**