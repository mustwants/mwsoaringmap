# Integration Dashboard

 

This repository now includes an integration dashboard that displays real-time information about all your GitHub repositories.

 

## Features

 

- **Live GitHub Data**: Fetches real-time data from GitHub API for all your repositories

- **Repository Overview**: Shows stars, forks, watchers, and open issues for each repo

- **Recent Commits**: Displays the 3 most recent commits for each repository

- **Activity Status**: Shows which repositories are actively maintained

- **Auto-Refresh**: Automatically updates every 5 minutes

- **Responsive Design**: Works beautifully on desktop and mobile devices

- **Security-First**: Includes comprehensive security headers and CSP

 

## Repositories Tracked

 

The dashboard tracks the following repositories:

- [mwsoaringmap](https://github.com/mustwants/mwsoaringmap)

- [calculators](https://github.com/mustwants/calculators)

- [doggypaddle](https://github.com/mustwants/doggypaddle)

- [mustsandwants](https://github.com/mustwants/mustsandwants)

- [cardflip](https://github.com/mustwants/cardflip)

- [agentpage](https://github.com/mustwants/agentpage)

 

## Files

 

- **index.html**: The main dashboard page

- **soaringmap.html**: The original 3D soaring map application

- **netlify.toml**: Netlify deployment configuration

 

## Deployment to Netlify

 

### Method 1: Connect GitHub Repository (Recommended)

 

1. Go to [Netlify Dashboard](https://app.netlify.com/)

2. Click "Add new site" → "Import an existing project"

3. Choose "Deploy with GitHub"

4. Select the `mustwants/mwsoaringmap` repository

5. Configure build settings:

   - **Branch to deploy**: `claude/create-integration-011CUzspE6M6BtFyb8EbSBD2` (or your preferred branch)

   - **Build command**: (leave empty)

   - **Publish directory**: `.`

6. Click "Deploy site"

 

Netlify will automatically:

- Deploy from the root directory

- Serve `index.html` as the homepage (dashboard)

- Make `soaringmap.html` available at `/soaringmap.html`

- Apply all security headers from `netlify.toml`

- Redeploy automatically when you push changes

 

### Method 2: Manual Deploy

 

If you prefer manual deployment:

 

1. Download/clone this repository

2. Go to [Netlify Drop](https://app.netlify.com/drop)

3. Drag and drop the folder

4. Your site will be deployed instantly

 

### Connecting to Your Existing Netlify Project

 

To use your existing "featuretesting" project:

 

1. Go to https://app.netlify.com/projects/featuretesting

2. Go to "Site configuration" → "Build & deploy"

3. Click "Link repository" or "Configure deploys"

4. Connect this GitHub repository

5. Set the branch to deploy from

 

## Usage

 

Once deployed, you'll have two pages:

 

1. **Dashboard** (index.html): Visit your Netlify URL directly

   - Example: `https://featuretesting.netlify.app/`

   - Shows overview of all repositories

 

2. **3D Soaring Map** (soaringmap.html): Visit `/soaringmap.html`

   - Example: `https://featuretesting.netlify.app/soaringmap.html`

   - Interactive 3D map application

 

## GitHub API Rate Limits

 

The dashboard uses the GitHub API which has rate limits:

- **Unauthenticated requests**: 60 requests per hour per IP address

- **Authenticated requests**: 5,000 requests per hour

 

For a 6-repository dashboard with auto-refresh every 5 minutes:

- Requests per refresh: ~18 (3 per repo)

- Refreshes per hour: 12

- Total requests per hour: ~216

 

**Recommendation**: If you expect high traffic or want higher limits, you can add a GitHub Personal Access Token (optional):

 

1. Go to GitHub Settings → Developer settings → Personal access tokens

2. Generate a new token with `public_repo` scope

3. Add it to the dashboard code in `index.html`:

 

```javascript

headers: {

    'Accept': 'application/vnd.github.v3+json',

    'Authorization': 'token YOUR_GITHUB_TOKEN'

}

```

 

4. **Important**: If you add a token, make sure to store it securely (use Netlify environment variables)

 

## Customization

 

### Adding More Repositories

 

Edit `index.html` and modify the `REPOS` array:

 

```javascript

const REPOS = [

    'mwsoaringmap',

    'calculators',

    'doggypaddle',

    'mustsandwants',

    'cardflip',

    'agentpage',

    'your-new-repo'  // Add more repos here

];

```

 

### Changing Refresh Interval

 

Modify the `CACHE_DURATION` constant (in milliseconds):

 

```javascript

const CACHE_DURATION = 5 * 60 * 1000; // 5 minutes

```

 

### Styling

 

All CSS is in the `<style>` section of `index.html`. Customize colors, fonts, and layout as needed.

 

## Security

 

The dashboard includes:

- Content Security Policy (CSP)

- X-Frame-Options protection

- X-Content-Type-Options protection

- No authentication tokens in client-side code by default

- Input sanitization for all GitHub data

 

## Browser Support

 

- Chrome/Edge (latest)

- Firefox (latest)

- Safari (latest)

- Mobile browsers

 

## Troubleshooting

 

### Dashboard shows "Error Loading Repositories"

 

1. Check your internet connection

2. Verify the repository names are correct

3. Check browser console for specific error messages

4. You may have hit GitHub API rate limits (wait an hour)

 

### Dashboard is blank

 

1. Open browser developer console (F12)

2. Look for JavaScript errors

3. Verify CSP isn't blocking GitHub API requests

4. Try refreshing the page

 

## Future Enhancements

 

Potential features to add:

- 📊 Contribution graphs

- 🔔 Deployment status indicators

- 📈 Traffic analytics (if using GitHub API with authentication)

- 🏷️ Release information

- 🌳 Branch information

- 👥 Contributor lists

- 📝 Issue and PR details

 

## License

 

Same as the parent repository.

 

## Support

 

For issues or questions, please open an issue on the GitHub repository.
