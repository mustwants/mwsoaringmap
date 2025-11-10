# QUICK REFERENCE CARD 🎯

## To Get Started in 3 Easy Steps:

### 1️⃣ Get Mapbox Token (FREE)
→ Go to: https://account.mapbox.com/
→ Sign up (no credit card needed)
→ Copy your token (starts with "pk.eyJ...")

### 2️⃣ Edit the HTML File
→ Open: 3d-soaring-map.html
→ Find line 191: `mapboxgl.accessToken = '...'`
→ Replace with YOUR token
→ Save

### 3️⃣ Open & Enjoy!
→ Double-click the HTML file
→ It opens in your browser
→ Start exploring!

---

## Property Template (Copy & Paste)

```javascript
,
{
    coordinates: [-118.2437, 34.0522],
    name: "Your Property Name",
    price: "$XXX,XXX",
    beds: 5,
    baths: 4,
    sqft: "4,200",
    agent: "Agent Name",
    phone: "(555) 555-5555",
    social: { fb: "📘", ig: "📷", tw: "🐦" }
}
```

**Find coordinates:** https://www.latlong.net/

---

## Common Edits

| What to Change | Line # | Example |
|---------------|--------|---------|
| Map Center | 196 | `center: [-98.5795, 39.8283]` |
| Starting Zoom | 197 | `zoom: 4` |
| Map Style | 195 | `'mapbox://styles/mapbox/...'` |
| Pin Color | 218 | `#667eea 0%, #764ba2 100%` |

---

## Troubleshooting

❌ **Map won't load** → Add your Mapbox token
❌ **Pins missing** → Check coordinate format [long, lat]
❌ **Error messages** → Check for missing commas

---

**That's it! Everything else is in the detailed README.md**