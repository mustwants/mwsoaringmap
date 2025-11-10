# Integration Hub - Interactive Testing Guide

The Integration Hub is designed as a **central testing environment** where you can interact with and test all your projects without leaving the hub!

## 🎮 How It Works

The hub embeds each project as a **live, interactive iframe** directly in the dashboard. Users can:
- Test projects right in the hub (400px preview)
- Click "Fullscreen" to test in full size
- Interact with all features directly
- Switch between projects instantly

## Quick Setup (5 Minutes Per Project)

### Enable GitHub Pages for Interactive Testing

**This is the recommended approach for the Integration Hub!**

For each repository:

1. Go to: `https://github.com/mustwants/[repo-name]/settings/pages`
2. Under **"Source"**: Select **"Deploy from a branch"** → **"main"**
3. Click **Save**
4. Wait 1-2 minutes for deployment
5. Your project is now live at: `https://mustwants.github.io/[repo-name]/`
6. The Integration Hub will automatically embed it!

**The hub is already configured with the correct URLs** - just enable GitHub Pages and refresh the hub!

### Option 2: Add Screenshots

To show actual screenshots instead of placeholders:

1. **Take screenshots** of your projects:
   - Open each project in a browser
   - Take a screenshot (recommended size: 1200x630px)
   - Save as PNG or JPG

2. **Upload screenshots**:
   - Option A: Add to this repository in a `screenshots/` folder
   - Option B: Upload to a image hosting service (imgur, cloudinary, etc.)
   - Option C: Use GitHub's repository social preview images

3. **Update the code**:
   ```javascript
   'calculators': {
       // ... other fields
       screenshotUrl: './screenshots/calculators.png',
       // or
       screenshotUrl: 'https://imgur.com/your-image.png',
       // ... other fields
   }
   ```

### Option 3: Enable GitHub Pages for Each Project

If you haven't deployed your projects yet, enable GitHub Pages:

1. Go to each repository on GitHub
2. Settings → Pages
3. Source: Deploy from branch → select `main` or `master`
4. Click Save
5. Your project will be available at: `https://mustwants.github.io/[repo-name]/`

Then update the `demoUrl` in `PROJECT_METADATA` with these URLs.

## Current Setup

The Integration Hub already has placeholder URLs for your projects:

- **mwsoaringmap**: ✅ Has live demo (./soaringmap.html) embedded
- **calculators**: 🔗 Demo URL placeholder: `https://mustwants.github.io/calculators/`
- **doggypaddle**: 🔗 Demo URL placeholder: `https://mustwants.github.io/doggypaddle/`
- **mustsandwants**: 🔗 Demo URL placeholder: `https://mustwants.github.io/mustsandwants/`
- **cardflip**: 🔗 Demo URL placeholder: `https://mustwants.github.io/cardflip/`
- **agentpage**: 🔗 Demo URL placeholder: `https://mustwants.github.io/agentpage/`

## Advanced: Embedding Projects

For projects you want to embed directly (like mwsoaringmap):

1. Set `useIframe: true` in PROJECT_METADATA
2. Make sure the project allows being embedded (check CSP and X-Frame-Options)
3. The dashboard will embed a live, interactive preview!

Example:
```javascript
'mwsoaringmap': {
    demoUrl: './soaringmap.html',
    useIframe: true,  // Enables embedding
    // ... other fields
}
```

## Screenshot Specifications

For best results:
- **Resolution**: 1200x630px (Twitter/OG card size)
- **Format**: PNG (best quality) or JPG (smaller size)
- **Content**: Show the most interesting/unique part of your project
- **Aspect Ratio**: 16:9 or 1.91:1

## Taking Great Screenshots

1. **Full-page screenshots**: Use browser extensions like:
   - Awesome Screenshot
   - Full Page Screen Capture
   - Chrome DevTools (Cmd+Shift+P → "Capture full size screenshot")

2. **Make it look good**:
   - Clear browser cache for crisp rendering
   - Hide dev tools
   - Use incognito/private mode for clean browser UI
   - Show the project in action, not just the landing page

3. **Optimize images**:
   - Use TinyPNG or ImageOptim to reduce file size
   - Keep under 500KB for fast loading

## Folder Structure (Recommended)

If storing screenshots in this repo:

```
mwsoaringmap/
├── screenshots/
│   ├── calculators.png
│   ├── doggypaddle.png
│   ├── mustsandwants.png
│   ├── cardflip.png
│   └── agentpage.png
├── index.html
├── soaringmap.html
└── ...
```

Then update URLs:
```javascript
screenshotUrl: './screenshots/calculators.png'
```

## Need Help?

If you run into issues:
1. Check browser console for errors
2. Verify image URLs are accessible
3. Ensure CSP allows loading images from your host
4. Check that demo URLs are live and working

## Interactive Testing Features

The Integration Hub includes powerful testing capabilities:

### 🎮 Embedded Demos (400px Preview)
- Each project card shows a live, interactive embed
- Scroll through projects and test features directly
- No need to open new tabs or windows

### ⛶ Fullscreen Testing Mode
- Click "Fullscreen" button on any project
- Test the full application in a large overlay
- Press ESC or click "Close" to return to hub
- Seamlessly switch between projects

### 🎯 Control Buttons
- **Fullscreen**: Open demo in fullscreen overlay for full testing
- **New Tab**: Open project in separate browser tab
- All projects stay accessible in one central hub

### ✓ Interactive Demo Badge
Projects with live embeds show a green "✓ Interactive Demo" badge

## Quick Test

After enabling GitHub Pages:
1. Refresh the Integration Hub
2. You should see:
   - mwsoaringmap: Live embedded 3D map ✓
   - calculators: Interactive calculator embed ✓
   - doggypaddle: Animation demo ✓
   - mustsandwants: Priority manager ✓
   - cardflip: Card game embed ✓
   - agentpage: Landing page preview ✓
3. Click "Test in Fullscreen" to interact with each project
4. Use the hub to demo all your projects to users!

## Best Practices

1. **Enable GitHub Pages** for all repos to get interactive testing
2. Use **fullscreen mode** for thorough feature testing
3. Keep all projects in the hub for easy comparison
4. Use the hub as your **main demo interface** for showcasing work

## Troubleshooting

### "Failed to load demo"
- GitHub Pages is not enabled yet - go to repo Settings → Pages
- Wait 1-2 minutes after enabling Pages for deployment
- Check that the repo has an index.html or main HTML file

### Iframe shows blank page
- Check the project's CSP doesn't block iframe embedding
- Verify X-Frame-Options allows embedding
- Test the direct URL to ensure it loads correctly

### Fullscreen not working
- Check browser console for errors
- Ensure JavaScript is enabled
- Try a different browser (Chrome, Firefox, Safari, Edge)

---

Your Integration Hub is now a **fully interactive testing environment**! 🚀 Enable GitHub Pages and start testing all your projects in one place.
