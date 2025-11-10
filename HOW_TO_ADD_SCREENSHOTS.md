# How to Add Screenshots and Demos to Integration Hub

The Integration Hub is now set up to display visual previews of all your projects! Here's how to add them:

## Quick Start

### Option 1: Add Demo URLs (Easiest)

If your projects are already deployed (e.g., on GitHub Pages, Netlify, etc.):

1. Open `index.html`
2. Find the `PROJECT_METADATA` object (around line 608)
3. Update the `demoUrl` field for each project with the live URL

Example:
```javascript
'calculators': {
    // ... other fields
    demoUrl: 'https://your-username.github.io/calculators/',
    // ... other fields
}
```

The dashboard will automatically show a "Click to View Demo" preview that links to your live site!

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

## Quick Test

After adding screenshots/demos:
1. Open `index.html` in a browser
2. You should see:
   - mwsoaringmap: Live embedded 3D map
   - Other projects: Screenshots or demo links
3. Click "View Live Demo" buttons to test links

---

Once you've added your screenshots or demos, your Integration Hub will look amazing! 🚀
