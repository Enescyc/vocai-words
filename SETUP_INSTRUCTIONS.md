# 🚀 Quick Setup Guide

Follow these steps to publish your support website to GitHub Pages.

## Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Fill in:
   - **Repository name:** `vocaiwords-support`
   - **Description:** "Support website for VocaiWords app"
   - **Visibility:** ✅ Public
   - ❌ **DO NOT** initialize with README
3. Click **"Create repository"**

## Step 2: Push Your Code

Copy your GitHub username from the repository page, then run:

```bash
cd /Users/enes/Desktop/vocaiwords-support

# Replace YOUR_USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR_USERNAME/vocaiwords-support.git

git push -u origin main
```

**Example:**
```bash
git remote add origin https://github.com/enesahin/vocaiwords-support.git
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main** / **/ (root)**
   - Click **Save**

## Step 4: Wait for Deployment

- GitHub will build your site (takes 1-2 minutes)
- You'll see a green checkmark when ready
- Your URL will be: `https://YOUR_USERNAME.github.io/vocaiwords-support/`

## Step 5: Test Your Site

Visit these URLs to verify everything works:
- Main page: `https://YOUR_USERNAME.github.io/vocaiwords-support/`
- Privacy: `https://YOUR_USERNAME.github.io/vocaiwords-support/privacy.html`
- Terms: `https://YOUR_USERNAME.github.io/vocaiwords-support/terms.html`

## Step 6: Update App Store Connect

Use your GitHub Pages URL in App Store Connect:

1. **Support URL:**
   ```
   https://YOUR_USERNAME.github.io/vocaiwords-support/
   ```

2. **Privacy Policy URL:**
   ```
   https://YOUR_USERNAME.github.io/vocaiwords-support/privacy.html
   ```

3. **Marketing URL (optional):**
   ```
   https://YOUR_USERNAME.github.io/vocaiwords-support/
   ```

## 📧 Important: Update Email Addresses

Before publishing, update the support email in all files:

1. Open `index.html` - Find `support@vocaiwords.com` and replace with your email
2. Open `privacy.html` - Find `privacy@vocaiwords.com` and replace with your email
3. Open `terms.html` - Find `support@vocaiwords.com` and replace with your email

```bash
# After updating emails, commit and push:
git add .
git commit -m "Update support email addresses"
git push
```

## ⚖️ Important: Update Legal Info

In `terms.html`, replace `[Your Jurisdiction]` with your actual jurisdiction:
- Example: "California, USA"
- Example: "United Kingdom"
- Example: "European Union"

## ✅ Verification Checklist

- [ ] Repository created on GitHub
- [ ] Code pushed to GitHub
- [ ] GitHub Pages enabled
- [ ] Website loads correctly
- [ ] All links work (Privacy, Terms)
- [ ] Email addresses updated
- [ ] Jurisdiction updated in Terms
- [ ] URLs added to App Store Connect

## 🎉 You're Done!

Your support website is now live and ready for App Store submission!

---

## 🔄 Updating Content Later

To update your support pages:

```bash
cd /Users/enes/Desktop/vocaiwords-support

# Edit your files (index.html, privacy.html, etc.)

git add .
git commit -m "Update support content"
git push
```

Changes appear on your live site within 1-2 minutes!

## 🆘 Need Help?

If you encounter issues:
1. Check GitHub Actions tab for build errors
2. Verify GitHub Pages is enabled in Settings
3. Make sure repository is Public
4. Wait 5 minutes and refresh

## 📱 App Store Requirements Met

✅ Support URL (required)
✅ Privacy Policy URL (required for apps with user data)
✅ Terms of Service (required for subscription apps)
✅ Professional appearance
✅ Mobile responsive
✅ Fast loading
✅ No tracking or cookies
