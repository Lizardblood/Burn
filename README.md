# BURN - Roast or get Roasted

An interactive roasting game built with vanilla HTML, CSS, and JavaScript. Features real-time performance monitoring with Vercel Speed Insights.

## Features

- **Interactive Roasting Game**: Submit your roasts and get AI-generated comebacks
- **Real-time Animations**: Flicking flames, floating silhouettes, and rising embers
- **Vercel Speed Insights Integration**: Built-in performance monitoring for Web Vitals
- **Lightweight**: Pure vanilla JavaScript with no external dependencies

## Getting Started

### Prerequisites

- Node.js and npm/pnpm/yarn/bun installed
- A Vercel account (for deployment and Speed Insights dashboard)
- Vercel CLI installed (optional, for local testing)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Lizardblood/Burn.git
cd Burn
```

2. Install dependencies:
```bash
pnpm install
# or npm install, yarn install, bun install
```

### Local Development

To run the development server:

```bash
pnpm dev
# or npm run dev
```

Open your browser and navigate to `http://localhost:3000` to see the game in action.

## Vercel Speed Insights Integration

This project includes Vercel Speed Insights for real-time performance monitoring. Speed Insights tracks Web Vitals (LCP, FID, CLS) and helps optimize your application's performance.

### How Speed Insights is Implemented

The Speed Insights integration is done via a simple script tag added to the HTML:

```html
<!-- Speed Insights initialization -->
<script>
  window.si =
    window.si ||
    function () {
      (window.siq = window.siq || []).push(arguments);
    };
</script>
<!-- Speed Insights script -->
<script defer src="/_vercel/speed-insights/script.js"></script>
```

This approach:
- ✅ Works with static HTML (no build step required)
- ✅ Automatically collects Web Vitals metrics
- ✅ Sends anonymized data to Vercel
- ✅ Respects user privacy settings

### Enabling Speed Insights on Vercel

1. **Create a Vercel project**:
   - Go to [Vercel Dashboard](https://vercel.com/dashboard)
   - Click "Add New" → "Project"
   - Select this repository

2. **Enable Speed Insights**:
   - Navigate to your project's settings
   - Find the "Speed Insights" tab
   - Click "Enable" to activate performance monitoring
   - Speed Insights routes will be available at `/_vercel/speed-insights/*` after next deployment

3. **Deploy to Vercel**:
```bash
vercel deploy
# or if connected via Git, deployments happen automatically on push
```

4. **View Your Data**:
   - Go to your project's Speed Insights dashboard
   - Monitor real-time and historical performance metrics
   - Use insights to optimize your application

## Performance Metrics Tracked

Speed Insights automatically captures:

- **LCP (Largest Contentful Paint)**: When the largest content element is rendered
- **FID (First Input Delay)**: Responsiveness to user interactions
- **CLS (Cumulative Layout Shift)**: Visual stability of the page
- **FCP (First Contentful Paint)**: When first content appears
- **TTFB (Time to First Byte)**: Server response time

## Project Structure

```
.
├── index.html           # Main HTML file with Speed Insights integration
├── package.json         # Project dependencies and scripts
└── README.md           # This file
```

## Technologies Used

- **HTML5**: Semantic markup with proper meta tags
- **CSS3**: Modern animations and styling
- **JavaScript (ES6+)**: Interactive game logic
- **Vercel Speed Insights**: Performance monitoring

## Deployment

### To Vercel

1. Connect your GitHub repository to Vercel
2. Vercel will automatically detect and deploy changes
3. Speed Insights will begin collecting data after deployment

### To Other Platforms

Since this is a static HTML site, you can deploy to any static hosting platform:
- Netlify
- GitHub Pages
- AWS S3
- Cloudflare Pages

**Note**: Speed Insights is Vercel-exclusive and requires Vercel hosting.

## Privacy & Compliance

Speed Insights respects privacy standards:
- No personal data is collected
- No cookies are set by Speed Insights
- Data collection respects Do Not Track signals
- Compliant with GDPR, CCPA, and other privacy regulations

For more details, see [Speed Insights Privacy Policy](https://vercel.com/docs/speed-insights/privacy-policy).

## Customization

To customize Speed Insights behavior, you can add a `beforeSend` function:

```html
<script>
  window.speedInsightsBeforeSend = function(data) {
    // Optionally remove sensitive information
    if (data.url) {
      data.url = data.url.split('?')[0]; // Remove query parameters
    }
    return data;
  };
</script>
```

## Troubleshooting

### Speed Insights Not Collecting Data

- Ensure Speed Insights is enabled in the Vercel dashboard
- Verify the script loads: check for `/_vercel/speed-insights/script.js` in Network tab
- Wait a few minutes - initial data takes time to appear
- Check that your app is deployed to Vercel (localhost won't send data)

### No Data in Dashboard

- Ensure users have visited your site after enabling Speed Insights
- Allow 24-48 hours for sufficient data to accumulate
- Verify your project has the Speed Insights feature enabled

## Resources

- [Vercel Speed Insights Documentation](https://vercel.com/docs/speed-insights)
- [Web Vitals Guide](https://web.dev/vitals/)
- [Performance Best Practices](https://web.dev/performance/)

## License

MIT

## Author

Lizardblood

---

**Roast or get Roasted** 🔥
