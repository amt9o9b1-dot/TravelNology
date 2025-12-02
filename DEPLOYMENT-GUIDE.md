# 🚀 Step-by-Step Deployment Guide

This guide will walk you through deploying your flight search landing page in under 10 minutes.

## ✅ What You Have

Your landing page is **100% ready to deploy** with:
- ✅ Amadeus API credentials already configured
- ✅ Delta & Alaska Airlines filtering
- ✅ Facebook Messenger integration ready
- ✅ Facebook Pixel tracking ready
- ✅ Mobile-responsive design
- ✅ Secure serverless backend

## 🎯 Quick Deploy Options

### Option A: Deploy to Vercel (Easiest - Recommended)

**Time: 5 minutes**

1. **Go to Vercel**
   - Visit: https://vercel.com/signup
   - Sign up with GitHub, GitLab, or Bitbucket

2. **Import Project**
   - Click "Add New..." → "Project"
   - Import your repository (or upload files)
   - Vercel will auto-detect the configuration

3. **Deploy**
   - Click "Deploy"
   - Wait 30-60 seconds
   - Done! You'll get a URL like: `https://your-project.vercel.app`

4. **Configure Facebook (Required)**
   - Edit your deployed `index.html`
   - Replace `YOUR_PIXEL_ID` with your Facebook Pixel ID
   - Replace `YOUR_PAGE_ID` with your Facebook Page ID
   - Save and redeploy

**Your site is now LIVE! 🎉**

---

### Option B: Deploy to Netlify

**Time: 5 minutes**

1. **Go to Netlify**
   - Visit: https://app.netlify.com/signup
   - Sign up with GitHub, GitLab, or Bitbucket

2. **Create New Site**
   - Click "Add new site" → "Import an existing project"
   - Connect your repository
   - Netlify will auto-detect the `netlify.toml` configuration

3. **Deploy**
   - Click "Deploy site"
   - Wait 30-60 seconds
   - Done! You'll get a URL like: `https://your-project.netlify.app`

4. **Configure Facebook (Required)**
   - Same as Vercel option above

**Your site is now LIVE! 🎉**

---

### Option C: Upload to Builderall

**Time: 10-15 minutes**

Since Builderall doesn't support serverless functions, you need a hybrid approach:

**Step 1: Deploy Backend to Vercel**
1. Create a Vercel account
2. Create a new project
3. Upload only the `api/` folder
4. Note your API URL: `https://your-api.vercel.app`

**Step 2: Update Frontend**
1. Edit `js/main.js`
2. Change line 6:
   ```javascript
   API_BASE_URL: 'https://your-api.vercel.app/api',
   ```

**Step 3: Upload to Builderall**
1. In Builderall, go to your website builder
2. Upload these files:
   - `index.html`
   - `css/style.css`
   - `js/main.js`
3. Maintain the folder structure

**Your site is now LIVE! 🎉**

---

## 🔧 Required Configuration

### 1. Get Facebook Pixel ID

1. Go to: https://business.facebook.com/events_manager
2. Select your Pixel (or create one)
3. Copy the Pixel ID (looks like: `1234567890123456`)
4. Replace in `index.html`:
   ```html
   fbq('init', 'YOUR_PIXEL_ID');
   ```

### 2. Get Facebook Page ID

1. Go to your Facebook Page
2. Click "About"
3. Scroll to find "Page ID"
4. Copy the ID
5. Replace in `index.html`:
   ```javascript
   chatbox.setAttribute("page_id", "YOUR_PAGE_ID");
   ```

### 3. Set Up Facebook Messenger

1. Go to: https://developers.facebook.com/docs/messenger-platform/discovery/customer-chat-plugin
2. Add your website URL to allowed domains
3. Configure automated greeting message
4. Test the chat widget

---

## 📊 Setting Up Facebook Ads

### 1. Create Ad Campaign

1. Go to Facebook Ads Manager
2. Create Campaign → Choose "Traffic" or "Conversions"
3. Set your target audience
4. Use your deployed URL as destination

### 2. Track Conversions

Your page already tracks these events:
- ✅ Page View
- ✅ Flight Search
- ✅ Book Now Click (InitiateCheckout)
- ✅ Messenger Opened

View them in Events Manager: https://business.facebook.com/events_manager

### 3. Optimize

- Use "Search" event for search optimization
- Use "InitiateCheckout" for conversion optimization
- Set up conversion campaigns after collecting data

---

## 🎯 Setting Up Propeller Ads

1. Create account: https://propellerads.com/
2. Create a new campaign
3. Choose campaign type:
   - **Push Notifications** (recommended for flights)
   - **Native Ads**
   - **Interstitials**
4. Set your landing page URL
5. Target by:
   - Geography (focus on US for Delta/Alaska)
   - Devices (mobile + desktop)
   - Interests (travel, vacation)

---

## ✅ Pre-Launch Checklist

Before sending traffic:

- [ ] Site is deployed and accessible
- [ ] Flight search works (test with LAX to SEA)
- [ ] Facebook Pixel ID is configured
- [ ] Facebook Page ID is configured
- [ ] Messenger chat widget appears
- [ ] Test on mobile device
- [ ] Test on different browsers (Chrome, Safari, Firefox)
- [ ] Facebook Pixel is firing (check in Events Manager)
- [ ] All external links work

---

## 🧪 Testing Your Deployment

### Test Flight Search

1. Visit your deployed site
2. Enter:
   - From: **LAX**
   - To: **SEA**
   - Departure: Tomorrow's date
   - Adults: 1
   - Class: Economy
3. Click "Search Flights"
4. You should see Delta and/or Alaska Airlines results

### Test Facebook Integration

1. Check browser console (F12)
2. Look for: `fbq` function calls
3. Open Facebook Events Manager
4. Go to "Test Events"
5. Visit your page - you should see events appear in real-time

### Test Messenger

1. Look for Messenger icon at bottom-right
2. Click it - chat window should open
3. Try sending a test message

---

## 🐛 Troubleshooting

### No Flight Results?

**Check:**
- Are you using test Amadeus API? (has limited availability)
- Try different routes (LAX-SEA, JFK-SEA, ATL-SEA)
- Try different dates (within next 30 days works best)
- Check browser console for errors

**Solution:** The test API has limited data. For full results, switch to production Amadeus API.

### Facebook Pixel Not Working?

**Check:**
- Pixel ID is correct (no spaces or quotes)
- View page source - search for your Pixel ID
- Use Facebook Pixel Helper extension

### Messenger Not Appearing?

**Check:**
- Page ID is correct
- Your website is added to allowed domains in Facebook
- Clear browser cache and reload

### API Errors?

**Check:**
- Backend is deployed (Vercel/Netlify)
- Environment variables are set
- Check deployment logs in Vercel/Netlify dashboard

---

## 📈 Monitoring Performance

### View Analytics

**Vercel:**
- Dashboard → Your Project → Analytics
- See page views, response times

**Netlify:**
- Site → Analytics
- See bandwidth, page views

**Facebook:**
- Events Manager → Your Pixel
- See all tracked events and conversions

### Key Metrics to Track

1. **Traffic**: Page views from ads
2. **Search Rate**: % of visitors who search
3. **Lead Rate**: % who click "Book Now" or open Messenger
4. **Cost Per Lead**: Ad spend / leads
5. **Conversion Rate**: Searches / visitors

---

## 🎨 Customization Tips

### Change Colors

Edit `css/style.css` (around line 16):
```css
:root {
    --primary-color: #0066ff;    /* Your brand color */
    --secondary-color: #00c2ff;  /* Accent color */
}
```

### Change Logo Text

Edit `index.html` (around line 51):
```html
<span>FlightFinder</span> <!-- Your company name -->
```

### Adjust Search Results

Edit `api/flight-search.js` (around line 105):
```javascript
max: '50', // Number of results (1-250)
```

---

## 💡 Pro Tips

1. **Start with small ad budgets** ($5-10/day) to test
2. **Focus on mobile traffic** - most travel searches are mobile
3. **Use urgency** in ad copy ("Limited seats!", "Prices rising!")
4. **A/B test headlines** and different ad creatives
5. **Retarget visitors** who searched but didn't book
6. **Set up automated Messenger responses** for common questions
7. **Monitor search patterns** to understand what routes are popular

---

## 🆘 Need Help?

**Amadeus API Issues:**
- Docs: https://developers.amadeus.com/
- Support: https://developers.amadeus.com/support

**Facebook/Messenger:**
- Docs: https://developers.facebook.com/docs/
- Support: https://developers.facebook.com/support/

**Vercel:**
- Docs: https://vercel.com/docs
- Support: https://vercel.com/support

**Netlify:**
- Docs: https://docs.netlify.com/
- Support: https://www.netlify.com/support/

---

## 🎉 You're Ready!

Your landing page is production-ready and optimized for conversions. 

**Next Steps:**
1. Deploy (choose Vercel, Netlify, or Builderall)
2. Configure Facebook Pixel and Messenger
3. Test everything
4. Launch your ad campaigns
5. Monitor and optimize

**Good luck with your campaigns! 🚀✈️**