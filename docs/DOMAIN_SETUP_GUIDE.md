# 🌐 Redirect piq.fi (Hostinger) to Vercel App

**Goal:** Make piq.fi point to your Vercel app (rwandatechacademy.com)

---

## ✅ Method 1: Custom Domain Setup (RECOMMENDED)

### Why This Method?
- ✅ Users see `piq.fi` in their browser (not rwandatechacademy.com)
- ✅ Better for SEO
- ✅ Faster (no redirect)
- ✅ SSL/HTTPS automatically provided by Vercel
- ✅ Professional appearance

---

## Step-by-Step Instructions

### 📍 STEP 1: Add Domain in Vercel

1. **Go to Vercel Dashboard**
   - URL: https://vercel.com/dashboard
   - Log in with your account

2. **Select Your Project**
   - Click on your project (the one hosting rwandatechacademy.com)

3. **Navigate to Domains**
   - Click **Settings** (top menu)
   - Click **Domains** (left sidebar)

4. **Add New Domain**
   - Click the **Add** button or **Add Domain** button
   - Enter: `piq.fi` (without www)
   - Click **Add**

5. **Vercel Will Show Configuration**
   - You'll see a message like "Configure DNS Records"
   - Vercel will show you specific DNS records
   - **Keep this page open** - you'll need these values!

6. **Add www Subdomain Too**
   - Repeat the process
   - Enter: `www.piq.fi`
   - Click **Add**

**Screenshot of what Vercel shows you:**
```
┌─────────────────────────────────────────────────┐
│ Add the following DNS records to piq.fi:       │
│                                                 │
│ Type: A                                         │
│ Name: @                                         │
│ Value: 76.76.21.21                             │
│                                                 │
│ Type: CNAME                                     │
│ Name: www                                       │
│ Value: cname.vercel-dns.com                    │
└─────────────────────────────────────────────────┘
```

**⚠️ Important:** Your actual IP/CNAME values might be different! Use the ones Vercel shows you.

---

### 📍 STEP 2: Log in to Hostinger

1. **Go to Hostinger**
   - URL: https://hostinger.com
   - Click **Login** (top right)

2. **Navigate to Domains**
   - Click **Domains** in the top menu
   - Or click **Domains** in the left sidebar

3. **Select piq.fi**
   - Find `piq.fi` in your domain list
   - Click **Manage** or click on the domain name

---

### 📍 STEP 3: Access DNS Settings

1. **Find DNS Zone Editor**
   - Look for one of these:
     - **DNS Zone**
     - **DNS / Nameservers**
     - **Manage DNS**
     - **DNS Records**
   - Click on it

2. **You Should See DNS Records Table**
   ```
   ┌──────────┬──────────┬─────────────────────┬──────┐
   │ Type     │ Name     │ Points to           │ TTL  │
   ├──────────┼──────────┼─────────────────────┼──────┤
   │ A        │ @        │ 123.45.67.89        │ 3600 │
   │ CNAME    │ www      │ piq.fi              │ 3600 │
   │ ...      │ ...      │ ...                 │ ...  │
   └──────────┴──────────┴─────────────────────┴──────┘
   ```

---

### 📍 STEP 4: Delete Old DNS Records

**IMPORTANT:** Remove existing records that conflict!

1. **Find and DELETE these records:**
   - ❌ Any **A record** with Name: `@` or blank
   - ❌ Any **CNAME record** with Name: `www`
   - ❌ Any **AAAA record** with Name: `@` (IPv6)

2. **How to Delete:**
   - Click the **trash icon** 🗑️ or **Delete** button next to each record
   - Confirm deletion

**⚠️ Don't delete these records (keep them):**
   - ✅ MX records (for email)
   - ✅ TXT records (for verification, SPF, DKIM)
   - ✅ NS records (nameservers)
   - ✅ Other records not related to @ or www

---

### 📍 STEP 5: Add New DNS Records (From Vercel)

Now add the records Vercel showed you in Step 1.

#### **Add A Record (Root Domain):**

1. Click **Add Record** or **Add New Record**
2. Fill in:
   ```
   Type: A
   Name: @ (or leave blank, or enter "piq.fi")
   Points to: 76.76.21.21 (⚠️ USE THE IP VERCEL GAVE YOU!)
   TTL: 3600 (or Auto)
   ```
3. Click **Save** or **Add Record**

#### **Add CNAME Record (www subdomain):**

1. Click **Add Record** again
2. Fill in:
   ```
   Type: CNAME
   Name: www
   Points to: cname.vercel-dns.com (⚠️ USE THE CNAME VERCEL GAVE YOU!)
   TTL: 3600 (or Auto)
   ```
3. Click **Save** or **Add Record**

**Your DNS records should now look like this:**
```
┌──────────┬──────────┬─────────────────────────┬──────┐
│ Type     │ Name     │ Points to               │ TTL  │
├──────────┼──────────┼─────────────────────────┼──────┤
│ A        │ @        │ 76.76.21.21             │ 3600 │
│ CNAME    │ www      │ cname.vercel-dns.com    │ 3600 │
│ MX       │ @        │ mail.hostinger.com      │ 3600 │
│ TXT      │ @        │ v=spf1 include:...      │ 3600 │
└──────────┴──────────┴─────────────────────────┴──────┘
```

---

### 📍 STEP 6: Remove Any Redirects/Forwarding

**Check if you have domain forwarding enabled:**

1. In Hostinger, look for:
   - **Domain Forwarding**
   - **Redirects**
   - **URL Forwarding**

2. If piq.fi has any redirects set up:
   - **Disable them** or **Delete them**

3. This is crucial! Redirects will conflict with DNS settings.

---

### 📍 STEP 7: Wait for DNS Propagation

**DNS changes take time:**
- ⏱️ Minimum: 5 minutes
- ⏱️ Average: 30 minutes to 2 hours
- ⏱️ Maximum: 48 hours (rare)

**Check Progress:**

1. **In Vercel Dashboard:**
   - Go to Settings → Domains
   - You'll see status next to piq.fi:
     - 🟡 **Pending** - DNS not propagated yet
     - ✅ **Valid** - DNS configured correctly!
     - ❌ **Invalid** - Something wrong (check records)

2. **Manual Check:**
   - Open browser in incognito/private mode
   - Visit: `http://piq.fi`
   - If it loads your app, it works! 🎉

---

### 📍 STEP 8: Verify SSL Certificate

Vercel automatically generates SSL certificates.

1. After DNS is verified, wait 5-10 minutes
2. Visit: `https://piq.fi` (with https)
3. Look for 🔒 padlock icon in browser
4. If you see it, SSL is working! ✅

---

### 📍 STEP 9: Set Primary Domain (Optional)

**If you want piq.fi to be the main domain:**

1. In Vercel → Settings → Domains
2. Find `piq.fi` in the list
3. Click the **three dots (⋮)** menu next to it
4. Select **Set as Primary Domain**

**What this does:**
- Automatically redirects rwandatechacademy.com → piq.fi
- Users always see piq.fi in their browser
- Good for brand consistency (IQ TECH ACADEMY → piq.fi)

---

## 🔍 Troubleshooting

### Problem: "Invalid Configuration" in Vercel

**Solution:**
- Double-check DNS records in Hostinger
- Make sure IP address matches exactly what Vercel shows
- Make sure CNAME matches exactly (including trailing dot if shown)
- Wait longer (DNS can take time)

### Problem: "This site can't be reached"

**Solution:**
- DNS hasn't propagated yet → Wait longer
- Clear browser cache: `Ctrl + Shift + Del`
- Try incognito mode
- Check DNS with online tool: https://www.whatsmydns.net (enter piq.fi)

### Problem: Shows old website or error

**Solution:**
- Redirects still enabled in Hostinger → Disable them
- Browser cache → Clear cache or use incognito
- DNS cached locally → Flush DNS:
  - Windows: `ipconfig /flushdns` in CMD
  - Mac: `sudo dscacheutil -flushcache` in Terminal
  - Linux: `sudo systemd-resolve --flush-caches`

### Problem: www.piq.fi works but piq.fi doesn't (or vice versa)

**Solution:**
- Both need separate DNS records
- Add A record for `@` (piq.fi)
- Add CNAME record for `www` (www.piq.fi)
- Both must be added in Vercel too

### Problem: SSL Certificate Error

**Solution:**
- Wait 10-15 minutes after DNS verification
- Vercel auto-generates SSL certificates
- If still not working after 1 hour:
  - Vercel Settings → Domains → Click domain → **Renew Certificate**

---

## 📊 Quick Reference Table

| Action | Where | What to Do |
|--------|-------|------------|
| Add Domain | **Vercel** | Add piq.fi and www.piq.fi |
| Get DNS Records | **Vercel** | Copy A record IP and CNAME value |
| Access DNS | **Hostinger** | Domains → piq.fi → DNS Zone |
| Delete Old | **Hostinger** | Remove A and CNAME for @ and www |
| Add New | **Hostinger** | Add A (@) and CNAME (www) from Vercel |
| Remove Redirects | **Hostinger** | Disable domain forwarding |
| Wait | **Anywhere** | 30 min - 2 hours |
| Verify | **Vercel** | Check green checkmark in Domains |
| Set Primary | **Vercel** | Optional: Set piq.fi as primary |

---

## 🎯 Expected DNS Records (Final State)

**In Hostinger DNS Zone for piq.fi:**

```
Type: A
Name: @
Value: 76.76.21.21 (or IP Vercel gave you)
TTL: 3600

Type: CNAME
Name: www
Value: cname.vercel-dns.com (or CNAME Vercel gave you)
TTL: 3600
```

**In Vercel Domains:**

```
✅ piq.fi → Valid
✅ www.piq.fi → Valid
```

---

## 📱 Test Your Setup

Once DNS propagates, test:

1. ✅ http://piq.fi → Loads your app
2. ✅ https://piq.fi → Loads with SSL (🔒)
3. ✅ http://www.piq.fi → Loads your app
4. ✅ https://www.piq.fi → Loads with SSL (🔒)
5. ✅ URL stays as piq.fi (doesn't change to rwandatechacademy.com)

---

## 🚀 After Setup

**Update your affiliate program materials:**
- Change all references from rwandatechacademy.com → **piq.fi**
- Update promotional materials
- Update social media links
- Update email signatures
- Update business cards

**piq.fi is much shorter and more memorable!** Perfect for marketing! 🎯

---

## 🆘 Still Having Issues?

**Check DNS Propagation:**
- https://www.whatsmydns.net
- Enter: piq.fi
- Select: A record
- Should show Vercel's IP globally

**Contact Support:**
- Vercel Support: https://vercel.com/support
- Hostinger Support: Live chat in dashboard

---

**Created:** January 2025
**For:** piq.fi → Vercel (rwandatechacademy.com)
**Status:** Production Ready
