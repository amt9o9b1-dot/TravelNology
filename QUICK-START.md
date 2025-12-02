# ⚡ Quick Start Guide

## 🎯 Deploy in 5 Minutes

### Fastest Route: Vercel

```bash
# Option 1: Using Vercel Website (No coding needed)
1. Go to https://vercel.com/signup
2. Click "Add New..." → "Project"
3. Upload your project folder or connect Git
4. Click "Deploy"
5. Done! Your site is live at https://your-project.vercel.app

# Option 2: Using Command Line
npm install -g vercel
vercel --prod
```

---

## ✏️ Required Edits (2 minutes)

### 1. Add Facebook Pixel ID
**File:** `index.html` (Line 17)

```javascript
fbq('init', 'YOUR_PIXEL_ID'); // ← Replace with your Pixel ID
```

**Get it here:** https://business.facebook.com/events_manager

---

### 2. Add Facebook Page ID
**File:** `index.html` (Line 212)

```javascript
chatbox.setAttribute("page_id", "YOUR_PAGE_ID"); // ← Replace with your Page ID
```

**Get it from:** Your Facebook Page → About → Page ID

---

## 🧪 Test It (2 minutes)

1. **Visit your site**
2. **Search for a flight:**
   - From: LAX
   - To: SEA
   - Date: Tomorrow
   - Click "Search Flights"
3. **Check results:** Should show Delta/Alaska flights
4. **Test Messenger:** Click chat icon (bottom-right)

---

## 📊 Launch Your Ads

### Facebook Ads
1. Go to https://business.facebook.com/adsmanager
2. Create Campaign → Traffic or Conversions
3. Use your Vercel URL as destination
4. Target: USA, Age 25-55, Interests: Travel
5. Budget: Start with $10-20/day

### Propeller Ads  
1. Go to https://propellerads.com/
2. Create Campaign → Push Notifications
3. Use your Vercel URL
4. Target: USA, Travel interests
5. Budget: Start with $5-10/day

---

## 📁 What You Have

```
✅ index.html              - Landing page
✅ css/style.css          - Styling
✅ js/main.js             - Frontend logic
✅ api/flight-search.js   - Amadeus API (backend)
✅ vercel.json            - Deployment config
✅ README.md              - Full documentation
```

---

## 🔧 Your API Credentials (Already Configured)

```
✅ AMADEUS_CLIENT_ID:     r6gJ8G7Cloc1vZNAFB6rz0GQHrcf4aHH
✅ AMADEUS_CLIENT_SECRET: 7YD56sAfZsfvzid8
```

These are **already set** in `vercel.json` - no action needed!

---

## ⚠️ Important Notes

### ⏰ Test API Limitations
You're using Amadeus **TEST API**:
- ✅ Free to use
- ⚠️ Limited flight data
- ⚠️ Some routes may have no results
- ℹ️ For full data, upgrade to Production API

**Best routes to test:**
- LAX → SEA
- JFK → SEA  
- ATL → LAX

### 🎯 Airlines Included
- ✈️ Delta Airlines (DL)
- 🛫 Alaska Airlines (AS)

To add more, edit `api/flight-search.js` line 13.

---

## 🐛 Quick Fixes

### No flight results?
- Try LAX to SEA
- Try tomorrow's date
- Check browser console (F12) for errors
- Test API is limited - normal to have few results

### Messenger not showing?
- Add your Page ID (see step 2 above)
- Whitelist your domain in Facebook settings
- Clear browser cache

### API not working?
- Check Vercel deployment logs
- Verify environment variables are set
- Test the backend: `https://your-site.vercel.app/api/flight-search`

---

## 📱 Mobile Testing

Your site is fully responsive! Test on:
- 📱 iPhone/Android
- 📱 Tablet
- 💻 Desktop

---

## 🎨 Quick Customization

### Change brand colors
**File:** `css/style.css` (Line 16-20)

### Change company name  
**File:** `index.html` (Line 51) - Look for "FlightFinder"

### Change results limit
**File:** `api/flight-search.js` (Line 105) - Change `max: '50'`

---

## 📈 Track Success

### View Performance
- **Vercel:** Dashboard → Analytics
- **Facebook:** Events Manager
- **Ads:** Facebook Ads Manager / Propeller Dashboard

### Key Metrics
- 👥 Visitors (traffic from ads)
- 🔍 Searches (how many search for flights)
- 💬 Leads (Messenger opens / bookings)
- 💰 Cost per lead

---

## ✅ Pre-Launch Checklist

- [ ] Site deployed to Vercel/Netlify
- [ ] Facebook Pixel ID added
- [ ] Facebook Page ID added
- [ ] Test search works (LAX → SEA)
- [ ] Messenger widget appears
- [ ] Tested on mobile
- [ ] Created Facebook Ads campaign
- [ ] Set up Propeller Ads campaign

---

## 🆘 Help & Resources

| Need Help With | Visit |
|---------------|-------|
| Full Documentation | `README.md` |
| Detailed Deployment | `DEPLOYMENT-GUIDE.md` |
| Amadeus API | https://developers.amadeus.com/ |
| Facebook Pixel | https://business.facebook.com/events_manager |
| Messenger Setup | https://developers.facebook.com/docs/messenger-platform/ |
| Vercel Support | https://vercel.com/support |

---

## 🚀 You're Ready!

1. ✅ Deploy to Vercel (5 min)
2. ✅ Add Facebook IDs (2 min)
3. ✅ Test (2 min)
4. ✅ Launch ads
5. ✅ Monitor and optimize

**Total time: ~10 minutes to launch!**

---

**Built for conversion. Optimized for paid traffic. Ready for scale.** 🎉✈️