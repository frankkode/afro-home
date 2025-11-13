# 🎨 IQ TECH ACADEMY - Affiliate Program Promotional Materials

Welcome! These are ready-to-use promotional materials for recruiting influencers to your affiliate program.

## 📁 Files Included

1. **promo-main-hero.html** - Main promotional page (desktop/presentation)
2. **promo-instagram-square.html** - Instagram post (1080x1080px)
3. **promo-instagram-story.html** - Instagram Story (1080x1920px)
4. **promo-facebook-wide.html** - Facebook post/cover (1200x630px)
5. **promo-how-it-works.html** - Infographic showing the process

## 🖼️ How to Convert HTML to Images

### Method 1: Screenshot (Easiest - Recommended)

**For Desktop/Laptop:**
1. Open the HTML file in Chrome or Firefox
2. Press `F11` to enter fullscreen mode
3. Take a screenshot:
   - **Windows**: Press `Windows + Shift + S` (Snipping Tool)
   - **Mac**: Press `Cmd + Shift + 4` (Select area)
   - **Linux**: Press `PrtScn` or use Screenshot tool
4. Save as PNG or JPG

**For Mobile Dimensions (Instagram):**
1. Open Chrome DevTools (`F12`)
2. Click the mobile device icon (toggle device toolbar)
3. Set custom dimensions:
   - Instagram Post: 1080 x 1080
   - Instagram Story: 1080 x 1920
4. Take screenshot using browser tools or:
   - Chrome: `Ctrl + Shift + P` → Type "screenshot" → "Capture screenshot"

### Method 2: Browser Screenshot Extensions

**Chrome Extensions (FREE):**
- **GoFullPage** - Full page screenshots
- **Awesome Screenshot** - Capture and edit
- **Nimbus Screenshot** - Professional captures

**Steps:**
1. Install extension from Chrome Web Store
2. Open HTML file in browser
3. Click extension icon
4. Select "Capture Visible Part" or "Full Page"
5. Download as PNG

### Method 3: Online Tools (No Installation)

**Option A: Screenshot.guru**
1. Go to https://screenshot.guru
2. Upload or paste HTML file
3. Set dimensions (1080x1080, 1200x630, etc.)
4. Download image

**Option B: HTML to Image Converter**
1. Go to https://htmlcsstoimage.com
2. Paste HTML code
3. Click "Create Image"
4. Download PNG

### Method 4: Command Line (For Developers)

**Using Puppeteer (Node.js):**

```bash
npm install puppeteer
```

Create `screenshot.js`:
```javascript
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();

  // Instagram Post
  await page.setViewport({ width: 1080, height: 1080 });
  await page.goto('file:///path/to/promo-instagram-square.html');
  await page.screenshot({ path: 'instagram-post.png' });

  // Instagram Story
  await page.setViewport({ width: 1080, height: 1920 });
  await page.goto('file:///path/to/promo-instagram-story.html');
  await page.screenshot({ path: 'instagram-story.png' });

  // Facebook
  await page.setViewport({ width: 1200, height: 630 });
  await page.goto('file:///path/to/promo-facebook-wide.html');
  await page.screenshot({ path: 'facebook-post.png' });

  await browser.close();
})();
```

Run:
```bash
node screenshot.js
```

## 📐 Recommended Dimensions for Each Platform

| Platform | File | Dimensions | Format |
|----------|------|------------|--------|
| Instagram Post | promo-instagram-square.html | 1080 x 1080 px | PNG/JPG |
| Instagram Story | promo-instagram-story.html | 1080 x 1920 px | PNG/JPG |
| Facebook Post | promo-facebook-wide.html | 1200 x 630 px | PNG/JPG |
| Twitter Post | promo-instagram-square.html | 1080 x 1080 px | PNG/JPG |
| LinkedIn Post | promo-facebook-wide.html | 1200 x 627 px | PNG/JPG |
| Email Header | promo-facebook-wide.html | 1200 x 630 px | PNG/JPG |
| Website Banner | promo-main-hero.html | Custom | PNG/JPG |
| Presentation | promo-how-it-works.html | 1920 x 1080 px | PNG/PDF |

## 🎯 Quick Start Guide

### For Non-Technical Users:

1. **Open HTML file** in your browser (Chrome recommended)
2. **Right-click** anywhere on the page → "Open in new window"
3. **Press F11** for fullscreen
4. **Take screenshot**:
   - Windows: `Windows Key + Shift + S`
   - Mac: `Cmd + Shift + 4`
5. **Save image** to your desktop
6. **Upload to social media** and start recruiting!

### For Technical Users:

Use the Puppeteer method above or browser dev tools for precise dimensions.

## 📱 How to Use These Images

### Instagram:
1. **Post** - Use `promo-instagram-square.html` screenshot
   - Caption: "💰 Join IQ TECH ACADEMY Affiliate Program! Earn 20-30% commission promoting quality tech education. Link in bio! #AffiliateProgram #TechEducation #Rwanda"

2. **Story** - Use `promo-instagram-story.html` screenshot
   - Add "Swipe Up" link to: www.rwandatechacademy.com/affiliate
   - Add sticker: "Apply Now"

### Facebook:
1. **Post** - Use `promo-facebook-wide.html` screenshot
   - Post text: "🚀 Calling all influencers and content creators! Join our affiliate program and earn 20-30% commission on every course sale. Easy approval, real-time tracking, fast payouts. Apply now at www.rwandatechacademy.com"

2. **Group Post** - Use `promo-how-it-works.html` screenshot
   - Share in influencer groups and tech communities

### Twitter/X:
1. Use `promo-instagram-square.html` screenshot
2. Tweet: "💰 Earn 20-30% promoting quality tech education! IQ TECH ACADEMY affiliate program is now open. ✅ Custom tracking links ✅ Real-time dashboard ✅ Fast payouts Apply: www.rwandatechacademy.com #AffiliateMarketing #TechEducation"

### Email:
1. Use `promo-main-hero.html` or `promo-how-it-works.html` screenshot
2. Send to your influencer database
3. Subject: "Exclusive Invitation: Join Our 30% Commission Affiliate Program"

### WhatsApp Business:
1. Use `promo-instagram-square.html` (works well on mobile)
2. Send to influencer contacts with message:
   "Hi! We're launching an affiliate program for IQ TECH ACADEMY. Earn 20-30% commission promoting tech courses. Interested? Check out the details in this image. Apply at www.rwandatechacademy.com"

## 🎨 Customization Tips

### Changing Colors:
Open HTML file in text editor and modify these CSS sections:
- **Primary gradient**: `#667eea` to `#764ba2` (purple)
- **Gold accent**: `#ffd700` to `#ffed4e` (yellow)
- Change to your brand colors as needed

### Changing Text:
- Open HTML file in any text editor
- Find the text you want to change
- Edit and save
- Re-screenshot

### Adding Your Logo:
1. Open HTML in text editor
2. Find `<div class="logo">IQ TECH ACADEMY</div>`
3. Replace with: `<img src="your-logo.png" alt="Logo">`
4. Adjust styling as needed

## 📧 Distribution Strategy

### Week 1: Social Media Blast
- Day 1: Instagram Post + Story
- Day 2: Facebook Post
- Day 3: Twitter/LinkedIn
- Day 4: Share in relevant groups
- Day 5: WhatsApp to influencer contacts

### Week 2: Email Campaign
- Send to influencer database
- Follow up with interested parties
- Schedule 1-on-1 calls

### Week 3: Paid Promotion
- Run Instagram/Facebook ads targeting influencers
- Use these images as ad creatives
- Target: Content creators, bloggers, YouTubers in Rwanda/East Africa

### Week 4: Partnerships
- Reach out to tech communities
- Share in Slack/Discord groups
- Partner with influencer networks

## 🎯 Target Audience for These Materials

Perfect for recruiting:
- ✅ Tech Influencers (Instagram, YouTube, TikTok)
- ✅ Bloggers & Content Creators
- ✅ Tech Community Leaders
- ✅ YouTubers (Tech Reviews, Tutorials)
- ✅ Podcast Hosts
- ✅ Newsletter Creators
- ✅ Social Media Managers
- ✅ Online Course Creators
- ✅ Tech Event Organizers

## 📊 Tracking Your Recruitment Campaign

Create a simple tracker:
```
Date | Platform | Image Used | Reach | Applications
-----|----------|------------|-------|-------------
Jan 15 | Instagram | Story | 5,000 | 12
Jan 16 | Facebook | Wide | 3,500 | 8
...
```

## 💡 Pro Tips

1. **Test on Mobile First** - Most influencers browse on mobile
2. **Use Hashtags** - #AffiliateProgram #TechEducation #Rwanda
3. **Add CTA Buttons** - "Apply Now", "Learn More", "Join Today"
4. **Create Urgency** - "Limited spots available"
5. **Show Social Proof** - "Join 50+ affiliates"
6. **A/B Test** - Try different images to see which performs better
7. **Follow Up** - Message interested influencers within 24 hours
8. **Offer Bonuses** - "First 10 affiliates get $50 signup bonus"

## 🚀 Next Steps

1. **Convert all 5 HTML files to images** using Method 1 (Screenshot)
2. **Upload to Google Drive/Dropbox** for easy sharing
3. **Create social media posts** using templates above
4. **Schedule posts** using Buffer, Hootsuite, or native schedulers
5. **Track applications** via your admin dashboard
6. **Approve qualified influencers** within 24-48 hours
7. **Onboard them** with welcome email and dashboard access

## 📞 Support

If you need custom designs or have questions:
- Email: support@rwandatechacademy.com
- Website: www.rwandatechacademy.com

---

**Created for:** IQ TECH ACADEMY Affiliate Program
**Updated:** January 2025
**Version:** 1.0

Good luck recruiting amazing affiliates! 🚀💰
