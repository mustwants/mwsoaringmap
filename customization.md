# COPY & PASTE CUSTOMIZATIONS 🎨

These are ready-to-use code snippets you can copy and paste into your HTML file.

---

## 🗺️ Different Map Styles

Replace line 195 with any of these:

### Satellite View (Current)
```javascript
style: 'mapbox://styles/mapbox/satellite-streets-v12',
```

### Modern Dark Theme
```javascript
style: 'mapbox://styles/mapbox/dark-v11',
```

### Clean Light Theme
```javascript
style: 'mapbox://styles/mapbox/light-v11',
```

### Outdoor/Topographic
```javascript
style: 'mapbox://styles/mapbox/outdoors-v12',
```

### Classic Streets
```javascript
style: 'mapbox://styles/mapbox/streets-v12',
```

---

## 🎨 Pin Color Themes

Replace line 218 with any of these:

### Ocean Blue
```javascript
background: linear-gradient(135deg, #4299e1 0%, #2c5282 100%);
```

### Sunset Orange
```javascript
background: linear-gradient(135deg, #fc466b 0%, #f76b1c 100%);
```

### Forest Green
```javascript
background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
```

### Royal Purple (Current)
```javascript
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Rose Gold
```javascript
background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
```

### Midnight Blue
```javascript
background: linear-gradient(135deg, #000428 0%, #004e92 100%);
```

---

## 📍 Major US Cities Coordinates

Copy these for your properties:

```javascript
// West Coast
Los Angeles:      [-118.2437, 34.0522]
San Francisco:    [-122.4194, 37.7749]
Seattle:          [-122.3321, 47.6062]
Portland:         [-122.6750, 45.5231]
San Diego:        [-117.1611, 32.7157]

// Southwest
Phoenix:          [-112.0740, 33.4484]
Las Vegas:        [-115.1398, 36.1699]
Denver:           [-104.9903, 39.7392]
Austin:           [-97.7431, 30.2672]
Dallas:           [-96.7970, 32.7767]

// Midwest
Chicago:          [-87.6298, 41.8781]
Minneapolis:      [-93.2650, 44.9778]
Kansas City:      [-94.5786, 39.0997]
St. Louis:        [-90.1994, 38.6270]
Detroit:          [-83.0458, 42.3314]

// Southeast
Miami:            [-80.1918, 25.7617]
Atlanta:          [-84.3880, 33.7490]
Orlando:          [-81.3792, 28.5383]
Charlotte:        [-80.8431, 35.2271]
Nashville:        [-86.7816, 36.1627]

// Northeast
New York:         [-74.0060, 40.7128]
Boston:           [-71.0589, 42.3601]
Philadelphia:     [-75.1652, 39.9526]
Washington DC:    [-77.0369, 38.9072]
Pittsburgh:       [-79.9959, 40.4406]
```

---

## 🏠 Sample Property Listings

Copy any of these complete property objects:

### Luxury Beach Home
```javascript
{
    coordinates: [-80.1918, 25.7617],
    name: "Oceanfront Paradise",
    price: "$3,900,000",
    beds: 6,
    baths: 5,
    sqft: "5,800",
    agent: "Maria Rodriguez",
    phone: "(305) 555-1234",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

### Downtown Condo
```javascript
{
    coordinates: [-87.6298, 41.8781],
    name: "Modern Urban Loft",
    price: "$650,000",
    beds: 2,
    baths: 2,
    sqft: "1,400",
    agent: "John Smith",
    phone: "(312) 555-5678",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

### Suburban Family Home
```javascript
{
    coordinates: [-97.7431, 30.2672],
    name: "Spacious Family Estate",
    price: "$725,000",
    beds: 5,
    baths: 3,
    sqft: "3,600",
    agent: "Lisa Johnson",
    phone: "(512) 555-9012",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

### Mountain Retreat
```javascript
{
    coordinates: [-104.9903, 39.7392],
    name: "Rocky Mountain Cabin",
    price: "$1,200,000",
    beds: 4,
    baths: 3,
    sqft: "2,800",
    agent: "Mike Peterson",
    phone: "(303) 555-3456",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

---

## 🎯 Starting Positions

Replace lines 196-197 with any of these:

### Entire USA View
```javascript
center: [-98.5795, 39.8283],
zoom: 4,
```

### West Coast Focus
```javascript
center: [-120.0, 37.5],
zoom: 6,
```

### East Coast Focus
```javascript
center: [-77.0, 40.0],
zoom: 6,
```

### Texas Focus
```javascript
center: [-99.0, 31.0],
zoom: 6,
```

### Florida Focus
```javascript
center: [-81.5, 28.0],
zoom: 7,
```

### Single City Close-up (NYC)
```javascript
center: [-74.0060, 40.7128],
zoom: 12,
```

---

## ⚡ Speed & Performance Settings

### Faster Animation (More Responsive)
Replace line 352:
```javascript
targetPitch = Math.min((zoom - 5) * 12, 60);
```

### Slower Animation (Smoother, Cinematic)
Replace line 352:
```javascript
targetPitch = Math.min((zoom - 5) * 5, 60);
```

### More Dramatic Tilt
Replace line 352:
```javascript
targetPitch = Math.min((zoom - 5) * 10, 75);
```

### Minimal Tilt (Mostly Top-Down)
Replace line 352:
```javascript
targetPitch = Math.min((zoom - 5) * 4, 30);
```

---

## 🎪 Cursor Effects

### Larger Cursor
Replace lines 26-29:
```javascript
#custom-cursor {
    width: 60px;
    height: 60px;
```

### Smaller Cursor
Replace lines 26-29:
```javascript
#custom-cursor {
    width: 30px;
    height: 30px;
```

### Different Cursor Color
Replace line 31:
```javascript
border: 3px solid #4299e1;  /* Blue cursor */
```

---

## 💳 Info Card Colors

### Blue Theme
Replace line 77:
```javascript
background: linear-gradient(135deg, #4299e1 0%, #2c5282 100%);
```

### Green Theme
```javascript
background: linear-gradient(135deg, #48bb78 0%, #2f855a 100%);
```

### Red Theme
```javascript
background: linear-gradient(135deg, #fc8181 0%, #c53030 100%);
```

### Dark Theme
```javascript
background: linear-gradient(135deg, #2d3748 0%, #1a202c 100%);
```

---

## 📏 Instructions Box Position

Current position is top-left. To change:

### Top Right
Replace lines 127-128:
```javascript
top: 20px;
right: 20px;
```

### Bottom Left
Replace lines 127-128:
```javascript
bottom: 20px;
left: 20px;
```

### Hide Instructions Box
Replace line 127:
```javascript
display: none;
```

---

## 🎬 Enable Constant Rotation

Find line 389 and remove the `//` at the start:
```javascript
rotateCamera();  // Now it will constantly rotate!
```

**Note:** This makes the map slowly rotate even when you're not moving the mouse. Great for display mode!

---

**Pro Tip:** Make one change at a time and refresh your browser to see the effect!