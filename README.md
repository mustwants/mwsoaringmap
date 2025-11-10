# mwsoaringmap
# 3D Soaring Real Estate Map - Setup Guide

## 🎯 What You Get

A beautiful 3D map with:
- **Soaring camera movement** that follows your mouse
- **Dynamic zoom** with automatic camera angle adjustments
- **Bird's-eye view** with horizon when zoomed in
- **8 sample real estate pins** across major US cities
- **Elegant info cards** showing property details when you hover
- **Custom floating cursor** effect
- **3D terrain** with atmospheric sky

---

## 🚀 Quick Start (3 Steps)

### Step 1: Get Your FREE Mapbox Token

1. Go to: https://account.mapbox.com/
2. Click "Sign Up" (it's FREE - no credit card needed for basic use)
3. After signing in, you'll see your **Access Token** on the dashboard
4. Copy the token (starts with "pk.eyJ...")

### Step 2: Add Your Token to the File

1. Open `3d-soaring-map.html` in a text editor (Notepad, TextEdit, etc.)
2. Find line 191 (near the top of the script section):
   ```javascript
   mapboxgl.accessToken = 'pk.eyJ1IjoiZXhhbXBsZXMiLCJhIjoiY2p0MG01MXRqMW45cjQzb2R6b2ptc3J4MSJ9.zA2W0IkI0c6KaAhJfk9bWg';
   ```
3. Replace the text between the quotes with YOUR token
4. Save the file

### Step 3: Open in Browser

1. Double-click the HTML file
2. It will open in your default web browser
3. Start exploring!

---

## 🎮 How to Use

- **Mouse Wheel** = Zoom in/out (watch the camera tilt!)
- **Move Mouse** = Slight camera rotation (soaring effect)
- **Hover on Pins** = See property information
- **Watch bottom-right** = See current zoom level and altitude

---

## ✏️ Customizing Your Properties

### Adding Your Own Real Estate Listings

Find the `properties` array (starts around line 204). Here's the format:

```javascript
{
    coordinates: [-118.2437, 34.0522],  // [longitude, latitude]
    name: "Luxury Villa Los Angeles",
    price: "$2,450,000",
    beds: 5,
    baths: 4,
    sqft: "4,200",
    agent: "Sarah Johnson",
    phone: "(310) 555-0123",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

### How to Get Coordinates

**Method 1: Google Maps**
1. Go to Google Maps
2. Right-click on the location
3. Click the coordinates at the top
4. Format: First number is longitude, second is latitude

**Method 2: LatLong.net**
1. Go to https://www.latlong.net/
2. Search for an address
3. Copy the coordinates

### Adding More Properties

Copy this template and add it to the properties array:

```javascript
,
{
    coordinates: [-XXX.XXXX, XX.XXXX],
    name: "Your Property Name",
    price: "$XXX,XXX",
    beds: X,
    baths: X,
    sqft: "X,XXX",
    agent: "Agent Name",
    phone: "(XXX) XXX-XXXX",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

**Important:** Put a comma BEFORE the opening brace (except for the first property)

---

## 🎨 Customization Options

### Change Starting Location

Find line 196:
```javascript
center: [-98.5795, 39.8283], // Center of USA
```
Change to your desired coordinates.

### Adjust Starting Zoom

Find line 197:
```javascript
zoom: 4,
```
- Lower number = zoomed out (1-2 = world view)
- Higher number = zoomed in (15+ = street level)

### Change Map Style

Find line 195. Options include:
```javascript
style: 'mapbox://styles/mapbox/satellite-streets-v12',  // Current (satellite)
style: 'mapbox://styles/mapbox/streets-v12',           // Streets
style: 'mapbox://styles/mapbox/dark-v11',              // Dark mode
style: 'mapbox://styles/mapbox/light-v11',             // Light mode
style: 'mapbox://styles/mapbox/outdoors-v12',          // Outdoor/terrain
```

### Change Pin Colors

Find line 218. Modify these colors:
```javascript
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

Popular color schemes:
- **Blue/Teal:** `#4299e1 0%, #2c5282 100%`
- **Red/Orange:** `#fc466b 0%, #3f5efb 100%`
- **Green/Blue:** `#11998e 0%, #38ef7d 100%`

### Adjust Camera Tilt Speed

Find line 352. Change the multiplier:
```javascript
targetPitch = Math.min((zoom - 5) * 8, 60);
```
- Higher number (e.g., `* 12`) = tilts faster
- Lower number (e.g., `* 5`) = tilts slower

---

## 🛠️ Troubleshooting

### Map doesn't load / "Please use your own token" error
- You need to add your Mapbox token (see Step 1-2 above)

### Pins don't appear
- Check that coordinates are in correct format: [longitude, latitude]
- Longitude is first (negative for Western hemisphere)
- Make sure all commas are in place between properties

### Info card doesn't show
- Make sure you're hovering directly over the pin
- Check browser console (F12) for errors

### Map is too slow
- Reduce number of properties (start with 5-10)
- Use a less detailed map style (streets instead of satellite)

---

## 📱 Browser Compatibility

Works best in:
- Chrome (recommended)
- Firefox
- Safari
- Edge

---

## 💡 Tips for Best Experience

1. **Start zoomed out** to see the soaring effect as you zoom in
2. **Move your mouse slowly** to see the gentle camera rotation
3. **Zoom gradually** to watch the camera angle change smoothly
4. **Hover over pins** to see the beautiful info cards
5. **Try different map styles** to match your brand

---

## 🎓 Learning Resources

- **Mapbox Documentation:** https://docs.mapbox.com/
- **Coordinate Finder:** https://www.latlong.net/
- **Color Picker:** https://coolors.co/
- **HTML Basics:** https://www.w3schools.com/html/

---

## 📄 Free Plan Limits

Mapbox FREE tier includes:
- 50,000 map loads per month
- More than enough for personal websites
- No credit card required

---

## Need Help?

Common issues are usually:
1. Missing or incorrect Mapbox token
2. Wrong coordinate format
3. Missing commas in properties array

If you need to start over, just re-download the original file!

---

**Enjoy your soaring map! 🚁✨**