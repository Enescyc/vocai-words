# App Store Resubmission Checklist

## 🎯 Issues to Fix

### ✅ Issue 1: Subscription Legal Links (FIXED)
**Apple's Requirement:** Apps with auto-renewable subscriptions must include functional links to Privacy Policy and Terms of Use in the app binary.

**Our Solution:**
- ✅ Added clickable Privacy Policy and Terms links to PaywallView.swift
- ✅ Added clickable Privacy Policy and Terms links to ManageSubscriptionView.swift
- ✅ Links direct to: https://enescyc.github.io/vocai-words/privacy.html and terms.html
- ✅ Enhanced subscription cards to show "Auto-renewable monthly subscription"

**Files Modified:**
- `Views/Subscription/PaywallView.swift` (termsSection updated)
- `Views/Subscription/ManageSubscriptionView.swift` (legalLinksSection added)

---

### ✅ Issue 2: Account Deletion (FIXED - Guideline 5.1.1(v))
**Apple's Requirement:** Apps with account creation must offer in-app account deletion.

**Our Solution:**
- ✅ Multi-step confirmation flow (3 steps)
- ✅ Shows deletion impact summary
- ✅ Important warnings with confirmation toggle
- ✅ Type "DELETE" to confirm
- ✅ Permanent deletion from all devices via CloudKit
- ✅ Privacy Policy updated with account deletion section

**Implementation:**
- `Backend/Application/Services/AccountDeletionService.swift`
- `Backend/Application/UseCases/Account/DeleteAccountUseCase.swift`
- `ViewModels/AccountViewModel.swift`
- `Views/Profile/AccountSettingsView.swift`
- `Views/Profile/DeleteAccountView.swift`
- `Backend/Application/DependencyContainer.swift` (wired dependencies)
- `Views/RootView.swift` (added navigation)
- `/Desktop/vocaiwords-support/privacy.html` (updated)

**User Flow:**
Profile → Account (gear icon) → Delete Account → 3-step confirmation → Permanent deletion

---

## 📋 App Store Connect Checklist

### Before Submission:

#### 1. App Description
- [ ] Copy subscription text from `APP_STORE_SUBSCRIPTION_DESCRIPTION.md`
- [ ] Paste at the end of App Information → Description
- [ ] Use the detailed version (or shorter version if hitting character limit)

#### 2. Privacy Policy URL (REQUIRED!)
- [ ] Go to App Information → Privacy Policy URL
- [ ] Enter: `https://enescyc.github.io/vocai-words/privacy.html`
- [ ] Click "Save"

#### 3. In-App Purchases
- [ ] Go to Features → In-App Purchases
- [ ] Select "Learner - Monthly Subscription" (com.vocaiwords.plus.monthly)
  - Display Name: "Learner - Monthly Subscription"
  - Description: "Enhanced learning with 180 AI word enrichments, 30 stories, and 90 recommendations per month. All game modes unlocked. Monthly auto-renewable subscription."
- [ ] Select "Master - Monthly Subscription" (com.vocaiwords.premium.monthly)
  - Display Name: "Master - Monthly Subscription"
  - Description: "Premium learning with 300 AI word enrichments, 100 stories, and 200 recommendations per month. All features unlocked with early access to new features. Monthly auto-renewable subscription."

#### 4. Build Upload
- [ ] Archive app with Xcode (Product → Archive)
- [ ] Upload to App Store Connect
- [ ] Wait for processing (usually 10-30 minutes)
- [ ] Select the new build in App Store Connect

#### 5. Submission Notes
Add this to "Notes for Review":

```
Fixed Issues:

1. Subscription Legal Links:
   - Added functional Privacy Policy and Terms of Use links in PaywallView
   - Added legal links in ManageSubscriptionView
   - Links are clickable and direct to hosted documents

2. Account Deletion (Guideline 5.1.1(v)):
   - Implemented in-app account deletion feature
   - Located at: Profile → Account Settings → Delete Account
   - Multi-step confirmation process prevents accidental deletion
   - All user data permanently deleted from all devices via CloudKit
   - Privacy Policy updated with detailed account deletion section

Test Account (if needed):
Email: [your test account email if you have one]
Password: [your test account password]

All subscription features can be tested with StoreKit Configuration in Xcode.
Privacy Policy: https://enescyc.github.io/vocai-words/privacy.html
Terms of Use: https://enescyc.github.io/vocai-words/terms.html
```

---

## ✅ Final Pre-Submission Verification

### In-App Verification:
- [ ] Build and run app on simulator/device
- [ ] Navigate to Paywall - verify Privacy and Terms links work
- [ ] Navigate to Manage Subscription - verify legal links work
- [ ] Navigate to Profile → Account Settings
- [ ] Try account deletion flow (don't complete on real account!)
- [ ] Verify all 3 deletion steps appear correctly
- [ ] Check subscription details show "Auto-renewable monthly subscription"

### App Store Connect Verification:
- [ ] Privacy Policy URL is set
- [ ] App Description includes subscription information
- [ ] Subscription display names are correct
- [ ] Subscription descriptions mention "auto-renewable monthly"
- [ ] Build is processed and selected
- [ ] Screenshots are up to date (if needed)

### Legal Documents Verification:
- [ ] Privacy Policy accessible: https://enescyc.github.io/vocai-words/privacy.html
- [ ] Privacy Policy includes Account Deletion section
- [ ] Terms of Use accessible: https://enescyc.github.io/vocai-words/terms.html
- [ ] Both documents load properly in mobile browsers

---

## 📊 Current Features & Limits

### Free Starter Plan:
- 25 AI word enrichments per month
- 5 AI-generated stories per month
- 10 word recommendations per month
- Basic game modes

### Learner ($4.99/month):
- 180 AI word enrichments per month
- 30 AI-generated stories per month
- 90 word recommendations per month
- All game modes
- Priority support

### Master ($9.99/month):
- 300 AI word enrichments per month
- 100 AI-generated stories per month
- 200 word recommendations per month
- All features unlocked
- Priority support
- Early access to new features

---

## 🚀 Ready to Submit!

Once all checkboxes above are completed:

1. Go to App Store Connect → My Apps → VocaiWords
2. Click on the version you're submitting
3. Scroll to "Submit for Review" button
4. Answer all questions (export compliance, advertising identifier, etc.)
5. Click "Submit"

**Estimated Review Time:** 24-48 hours (typically)

**What Apple Will Check:**
- ✅ Subscription has legal links in app binary
- ✅ Account deletion works in-app
- ✅ Privacy Policy URL accessible
- ✅ Subscription information clear and accurate

---

## 📞 If Apple Rejects Again

If rejected, check:
1. The exact rejection reason in Resolution Center
2. Whether links are actually clickable (not just displayed text)
3. Whether Privacy Policy URL in App Store Connect matches the in-app URL
4. Whether account deletion actually works (test it!)
5. Review this checklist again

Common issues:
- Privacy Policy URL not set in App Store Connect metadata
- Links in app not clickable (using Text instead of Link)
- Account deletion feature not discoverable
- Subscription auto-renewal terms not clear enough

---

**Good luck! 🍀**

Last updated: October 3, 2025
