# Flight Price Landing Page 🛫

A professional, conversion-optimized landing page for searching flight prices from **Delta Airlines** and **Alaska Airlines** using the Amadeus API. Designed for paid traffic from Propeller Ads and Facebook Ads with integrated lead capture through Facebook Messenger.

![Flight Search Landing Page](https://img.shields.io/badge/Status-Production%20Ready-green)
![Node.js](https://img.shields.io/badge/Node.js-18+-blue)
![Amadeus API](https://img.shields.io/badge/Amadeus-API%20v2-orange)

## 🌟 Features

### ✈️ Core Functionality
- **Real-time flight search** using Amadeus API
- **Filter results** for Delta (DL) and Alaska Airlines (AS) only
- **Flexible search options**: One-way or round-trip flights
- **Travel class selection**: Economy, Premium Economy, Business, First Class
- **Multi-passenger support**: Search for 1-6 adults
- **Responsive design**: Optimized for mobile, tablet, and desktop

### 📊 Marketing & Conversion
- **Facebook Pixel integration** for conversion tracking
- **Facebook Messenger chat plugin** for lead capture
- **Conversion-optimized design** with clear CTAs
- **Professional UI/UX** built with modern web standards
- **Fast loading times** with minimal dependencies

### 🔒 Security
- **Server-side API credentials** - Never exposed to clients
- **Serverless architecture** for scalability and security
- **CORS protection** configurable per environment
- **Environment variable management**

## 📋 Currently Completed Features

✅ **Frontend Landing Page**
- Flight search form with validation
- Real-time date validation
- Loading states and error handling
- Flight results display with detailed information
- Messenger integration for lead capture
- Smooth scrolling navigation
- Mobile-responsive design

✅ **Backend API**
- Secure Amadeus API integration
- OAuth2 token management with caching
- Flight search with airline filtering
- Error handling and logging
- CORS support

✅ **Deployment Ready**
- Vercel configuration
- Netlify configuration
- Package.json for dependencies
- Environment variable management

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ (optional, for local development)
- Amadeus API credentials (already configured)
- Facebook Page ID and Pixel ID (for tracking)
- Vercel or Netlify account (for deployment)

### Option 1: Deploy to Vercel (Recommended)

1. **Install Vercel CLI** (optional for command-line deployment)
   ```bash
   npm install -g vercel
   ```

2. **Deploy the project**
   ```bash
   vercel --prod
   ```

3. **Or use Vercel Dashboard:**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import this repository
   - Click "Deploy"
   - Vercel will automatically detect the configuration

4. **Environment Variables** (already set in vercel.json, but you can override):
   - `AMADEUS_CLIENT_ID`: r6gJ8G7Cloc1vZNAFB6rz0GQHrcf4aHH
   - `AMADEUS_CLIENT_SECRET`: 7YD56sAfZsfvzid8

### Option 2: Deploy to Netlify

1. **Install Netlify CLI** (optional)
   ```bash
   npm install -g netlify-cli
   ```

2. **Deploy via Dashboard:**
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Connect your Git repository
   - Netlify will auto-detect the configuration from `netlify.toml`
   - Click "Deploy site"

3. **Or deploy via CLI:**
   ```bash
   netlify deploy --prod
   ```

### Option 3: Upload to Builderall or Any Web Host

For static hosting without serverless functions:

1. **Set up a separate backend:**
   - Deploy the `api/` folder to Vercel or Netlify separately
   - Get the API URL (e.g., `https://your-api.vercel.app`)

2. **Update frontend configuration:**
   - Edit `js/main.js`
   - Change `API_BASE_URL` to your backend URL:
     ```javascript
     const CONFIG = {
         API_BASE_URL: 'https://your-api.vercel.app/api',
     };
     ```

3. **Upload frontend files to Builderall:**
   - Upload: `index.html`, `css/`, `js/` folders
   - Ensure proper folder structure is maintained

## ⚙️ Configuration

### 1. Facebook Pixel Setup

Edit `index.html` and replace `YOUR_PIXEL_ID`:

```html
fbq('init', 'YOUR_PIXEL_ID'); // Replace with your Facebook Pixel ID
```

Also update the noscript tag:
```html
<img height="1" width="1" style="display:none"
src="https://www.facebook.com/tr?id=YOUR_PIXEL_ID&ev=PageView&noscript=1" />
```

### 2. Facebook Messenger Setup

Edit `index.html` and replace `YOUR_PAGE_ID`:

```javascript
chatbox.setAttribute("page_id", "YOUR_PAGE_ID"); // Replace with your Facebook Page ID
```

**How to get your Facebook Page ID:**
1. Go to your Facebook Page
2. Click "About"
3. Scroll down to find "Page ID"
4. Copy the numeric ID

### 3. Switch to Production Amadeus API

When ready for production (test API has limited features):

Edit `api/flight-search.js`:
```javascript
const AMADEUS_CONFIG = {
    // ...
    baseUrl: 'https://api.amadeus.com', // Change from test.api.amadeus.com
    // ...
};
```

And update your environment variables with production credentials.

## 📁 Project Structure

```
flight-price-landing-page/
├── index.html              # Main landing page
├── css/
│   └── style.css          # All styling
├── js/
│   └── main.js            # Frontend JavaScript
├── api/
│   └── flight-search.js   # Serverless API function
├── vercel.json            # Vercel configuration
├── netlify.toml           # Netlify configuration
├── package.json           # Project metadata
├── .env.example           # Environment variables template
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## 🔧 Local Development

1. **Install Vercel CLI for local testing:**
   ```bash
   npm install -g vercel
   ```

2. **Run local dev server:**
   ```bash
   vercel dev
   ```

3. **Access the site:**
   - Open browser to `http://localhost:3000`
   - API will be available at `http://localhost:3000/api/flight-search`

## 📊 Data Models

### Flight Search Request
```javascript
{
  origin: "LAX",              // 3-letter IATA code
  destination: "SEA",         // 3-letter IATA code
  departureDate: "2024-12-25", // YYYY-MM-DD
  returnDate: "2024-12-30",   // Optional, YYYY-MM-DD
  adults: 1,                  // 1-6 passengers
  travelClass: "ECONOMY"      // ECONOMY, PREMIUM_ECONOMY, BUSINESS, FIRST
}
```

### Flight Search Response
```javascript
{
  success: true,
  count: 15,                  // Number of flights found
  flights: [...],             // Array of flight offers
  dictionaries: {...},        // Airport/airline info
  searchParams: {...}         // Original search parameters
}
```

## 🎯 Conversion Tracking Events

The page tracks the following Facebook Pixel events:

- `PageView` - Landing page view
- `ViewContent` - Page initialization
- `Search` - Flight search performed
- `InitiateCheckout` - "Book Now" button clicked
- `MessengerOpened` - Messenger chat opened
- `NoFlightsFound` - No results for search (custom event)

## 🌐 API Endpoints

### POST /api/flight-search

Search for flights from Delta and Alaska Airlines.

**Request Body:**
```json
{
  "origin": "LAX",
  "destination": "SEA",
  "departureDate": "2024-12-25",
  "returnDate": "2024-12-30",
  "adults": 2,
  "travelClass": "ECONOMY"
}
```

**Response:**
```json
{
  "success": true,
  "count": 15,
  "flights": [...],
  "dictionaries": {...}
}
```

## 🛠️ Customization

### Change Brand Colors

Edit `css/style.css`:
```css
:root {
    --primary-color: #0066ff;      /* Main brand color */
    --secondary-color: #00c2ff;    /* Accent color */
    --dark-blue: #002857;          /* Dark variant */
}
```

### Add More Airlines

Edit `api/flight-search.js`:
```javascript
const ALLOWED_AIRLINES = ['DL', 'AS', 'UA', 'AA']; // Add airline codes
```

### Modify Results Limit

Edit `api/flight-search.js`:
```javascript
max: '50', // Change to desired number (1-250)
```

## 🚫 Features Not Yet Implemented

- [ ] Email lead capture form (currently using Messenger only)
- [ ] Multi-city flight searches
- [ ] Price alerts and notifications
- [ ] Seat selection visualization
- [ ] Booking completion (redirects to Messenger)
- [ ] User accounts and booking history
- [ ] Multi-language support
- [ ] Currency conversion
- [ ] Advanced filters (stops, departure times, airlines)
- [ ] Comparison with other airlines beyond Delta/Alaska

## 📈 Recommended Next Steps

1. **Set up Facebook Business Manager**
   - Create Facebook Page
   - Install Messenger plugin
   - Set up automated responses in Messenger

2. **Configure Ad Campaigns**
   - Create Facebook Ads with the landing page URL
   - Set up Propeller Ads campaigns
   - Use tracked events for optimization

3. **Monitor Performance**
   - Check Facebook Pixel data in Events Manager
   - Track conversion rates
   - A/B test different ad creatives

4. **Optimize for Conversions**
   - Adjust CTA copy based on performance
   - Test different headline variations
   - Optimize page load speed

5. **Scale Up**
   - Switch to production Amadeus API
   - Add more airline options
   - Implement additional payment options

## 🔐 Security Best Practices

1. **Never expose API credentials** in frontend code
2. **Use environment variables** for sensitive data
3. **Enable CORS restrictions** in production:
   ```javascript
   'Access-Control-Allow-Origin': 'https://yourdomain.com'
   ```
4. **Implement rate limiting** for API endpoints
5. **Use HTTPS** for all deployments

## 📞 Support & Documentation

- **Amadeus API Docs**: https://developers.amadeus.com/
- **Facebook Pixel**: https://developers.facebook.com/docs/facebook-pixel
- **Messenger Platform**: https://developers.facebook.com/docs/messenger-platform
- **Vercel Docs**: https://vercel.com/docs
- **Netlify Docs**: https://docs.netlify.com/

## 📄 License

MIT License - Free to use and modify for your projects.

## 🎉 Deployment Checklist

Before going live, make sure to:

- [ ] Add your Facebook Pixel ID
- [ ] Add your Facebook Page ID for Messenger
- [ ] Test flight search functionality
- [ ] Verify Messenger chat works
- [ ] Check mobile responsiveness
- [ ] Test on different browsers
- [ ] Set up conversion tracking in Facebook Ads Manager
- [ ] Configure production Amadeus API (when ready)
- [ ] Add custom domain (optional)
- [ ] Set up SSL certificate (automatic on Vercel/Netlify)

## 🚀 Live Demo

After deployment, your site will be available at:
- **Vercel**: `https://your-project.vercel.app`
- **Netlify**: `https://your-project.netlify.app`
- **Custom Domain**: Configure in hosting dashboard

---

**Built with ❤️ for converting paid traffic into flight bookings**

For questions or issues, feel free to open an issue or contact support.