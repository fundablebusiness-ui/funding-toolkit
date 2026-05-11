# 🚀 ShesFundable - Deployment Guide

Complete instructions for deploying ShesFundable sales pages to GitHub Pages or Systeme.io.

---

## Option 1: GitHub Pages (FREE)

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Create repository: `shesfundable.github.io`
3. Make it **public**
4. Click "Create repository"

### Step 2: Upload Files

**Option A: Using Git (Recommended)**
```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/shesfundable.github.io.git
cd shesfundable.github.io

# Copy all HTML files here
# Then commit and push
git add .
git commit -m "Initial ShesFundable pages"
git push origin main
```

**Option B: Using GitHub Web Interface**
1. Go to your repository
2. Click "Add file" → "Upload files"
3. Drag and drop all HTML files
4. Click "Commit changes"

### Step 3: Files to Upload

```
shesfundable.github.io/
├── index.html                          (homepage/hero)
├── funding-sales-page.html             (full sales page)
├── order.html                          (checkout form)
├── thank-you.html                      (post-purchase)
├── universal-footer.html               (shared footer)
├── README.md                           (documentation)
├── CNAME                               (custom domain)
└── .gitignore                          (git settings)
```

### Step 4: Custom Domain Setup

1. Update `CNAME` file with your domain:
   ```
   shesfundable.com
   ```

2. Go to domain registrar (GoDaddy, NameCheap, etc.)
3. Update DNS records to point to GitHub Pages:
   ```
   A record:  185.199.108.153
   A record:  185.199.109.153
   A record:  185.199.110.153
   A record:  185.199.111.153
   CNAME:     shesfundable.github.io
   ```

4. In GitHub repository:
   - Settings → Pages
   - Custom domain: `shesfundable.com`
   - Enforce HTTPS ✓

### Step 5: Verify Deployment

- Homepage: `https://shesfundable.com`
- Sales page: `https://shesfundable.com/funding-sales-page.html`
- Order: `https://shesfundable.com/order.html`
- Thank you: `https://shesfundable.com/thank-you.html`

---

## Option 2: Systeme.io (Recommended for Payment Processing)

### Step 1: Create New Pages in Systeme.io

1. Go to Systeme.io dashboard
2. Create new page: "Funding Toolkit Sales"
3. Use builder or switch to HTML editor

### Step 2: Add Sales Page

1. Click "Edit Page"
2. Click HTML/Code editor icon
3. Select all code from `funding-sales-page.html`
4. Paste entire HTML
5. Click "Save"

**Update button links:**
```html
<!-- Change this: -->
<a href="https://shesfundable.systeme.io/order" class="cta-primary">

<!-- To: -->
<a href="YOUR-CHECKOUT-URL" class="cta-primary">
```

### Step 3: Add Order Form Page

1. Create new page: "Order"
2. Switch to HTML editor
3. Paste `order.html` content
4. Update payment processor integration
5. Test checkout flow

### Step 4: Add Thank You Page

1. Create new page: "Thank You"
2. Switch to HTML editor
3. Paste `thank-you.html` content
4. Update download links to your toolkit files
5. Test with test transaction

### Step 5: Configure Payment

**If using Stripe:**
1. Settings → Payment Methods → Stripe
2. Enter API keys
3. Test payment flow

**If using PayPal:**
1. Settings → Payment Methods → PayPal
2. Enter credentials
3. Verify webhook endpoints

**If using Systeme.io Native:**
1. Settings → Payment Processing
2. Enable card processing
3. Set up email confirmations

### Step 6: Email Setup

**Order confirmation email:**
1. Automations → New workflow
2. Trigger: "New order"
3. Action: "Send email"
4. Template: Order confirmation + download links

**Welcome email:**
1. Automations → Newsletter
2. Add new subscribers to ShesNewsy list
3. Send welcome series

**Toolkit delivery:**
1. Automate file delivery after payment
2. Include download links in email
3. Add documentation PDFs

---

## Important Links to Update

### In All Pages
- Newsletter signup: `#` → Your newsletter signup URL
- Blog: `#` → Your blog URL
- Contact page: `#` → Your contact page

### In Sales Page
- CTA buttons: `https://shesfundable.systeme.io/order` → Your actual checkout URL

### In Order Form
- Payment processor API endpoints
- Email endpoints
- Webhook URLs
- Success redirect URL (thank-you page)

### In Thank You Page
- Toolkit download links
- Documentation links
- Support email address
- Newsletter signup URL

### In Footer (All Pages)
- Privacy Policy: `#` → /privacy-policy
- Terms & Conditions: `#` → /terms
- Refund Policy: `#` → /refund-policy
- Contact: `#` → /contact

---

## Legal Pages You Need to Create

Create these as separate pages/files:

### 1. Privacy Policy
```
📋 Required information:
- What data you collect
- How you use it
- Third-party sharing
- User rights
- Contact information
- Cookie policy
```

### 2. Terms & Conditions
```
📋 Required information:
- Product description
- Purchase terms
- Payment terms
- Disclaimer
- Limitation of liability
- Governing law
```

### 3. Refund Policy
```
📋 Required information:
- 30-day money-back guarantee
- How to request refund
- Refund processing time
- Non-refundable items (if any)
- Contact process
```

### 4. Disclaimer
```
📋 Required information:
- No guarantees
- Educational purposes only
- Not financial advice
- Not legal advice
- Past performance ≠ future results
- Individual results vary
```

**Create quickly using:**
- Termly.io (auto-generates)
- iubenda.com (GDPR compliant)
- Generic policy sites

---

## Testing Checklist

Before going live, test:

### 📱 Device Testing
- [ ] Desktop (1920px, 1366px)
- [ ] Tablet (768px)
- [ ] Mobile (375px)
- [ ] All browsers (Chrome, Safari, Firefox, Edge)

### 🔗 Link Testing
- [ ] All CTA buttons work
- [ ] Newsletter signup links
- [ ] Footer links active
- [ ] Legal pages accessible

### 💳 Payment Testing
- [ ] Credit card form validation
- [ ] PayPal flow works
- [ ] Test transaction succeeds
- [ ] Confirmation email sends
- [ ] Redirect to thank-you page

### 📧 Email Testing
- [ ] Order confirmation received
- [ ] Download links work
- [ ] Newsletter opt-in works
- [ ] Support email responds

### 🎨 Design Testing
- [ ] Colors display correctly
- [ ] Fonts load properly
- [ ] Images/icons render
- [ ] Animations smooth

---

## Performance Optimization

After deployment, optimize for speed:

### Sitemap (SEO)
```xml
<!-- Add to sitemap.xml -->
<urlset>
  <url><loc>https://shesfundable.com/</loc></url>
  <url><loc>https://shesfundable.com/funding-sales-page.html</loc></url>
  <url><loc>https://shesfundable.com/order.html</loc></url>
  <url><loc>https://shesfundable.com/thank-you.html</loc></url>
</urlset>
```

### robots.txt
```
User-agent: *
Allow: /
Disallow: /thank-you.html

Sitemap: https://shesfundable.com/sitemap.xml
```

### Analytics
- Add Google Analytics tracking
- Set up conversion goals
- Track form submissions
- Monitor page performance

---

## Troubleshooting

### Pages Not Showing
- [ ] Wait 5-10 minutes for deployment
- [ ] Clear browser cache (Ctrl+Shift+Delete)
- [ ] Check GitHub Pages settings are enabled
- [ ] Verify CNAME is configured correctly

### Buttons Not Working
- [ ] Check href URLs are correct
- [ ] Verify links point to actual pages
- [ ] Test in incognito mode
- [ ] Check browser console for errors

### Payment Not Processing
- [ ] Verify API keys are correct
- [ ] Check payment processor webhook settings
- [ ] Test with test card numbers
- [ ] Check logs for error messages

### Emails Not Sending
- [ ] Verify email configuration
- [ ] Check spam folder
- [ ] Verify sender email is correct
- [ ] Test with test email address

---

## Support

**Questions?**
- Email: support@shesfundable.com
- Check: README.md for detailed file descriptions
- Review: Inline comments in HTML files

---

## Final Checklist Before Launch

- [ ] All pages deployed and accessible
- [ ] All links tested and working
- [ ] Payment processing tested
- [ ] Email confirmations working
- [ ] Mobile responsive verified
- [ ] Legal pages created and linked
- [ ] Analytics installed
- [ ] Backup copies saved locally
- [ ] Domain properly configured
- [ ] HTTPS enabled
- [ ] Monitoring setup (error tracking)
- [ ] Support email configured

---

**You're ready to launch! 🚀**

Good luck with your ShesFundable launch!
