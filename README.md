# Manual QA Report — Glowy AI Mobile Application

> A comprehensive end-to-end manual QA audit of an AI-powered photo generation app, conducted across iOS and Android platforms.

---

## Overview

This repository contains a detailed manual quality assurance report for the **Glowy AI** mobile application (v5.6), an AI-based photo generation and editing app available on both the App Store and Google Play.

The testing was conducted as a freelance QA engagement, covering the full user journey from installation through payment flows, across two platforms and two physical devices.

**App Version:** 5.6  
**Platforms:** iOS and Android  
**Devices:** iPhone (iOS) / Xiaomi (Android)

---

## Scope of Testing

| Area | Tested |
|---|---|
| App Store installation & discoverability | ✅ |
| Storage capacity & battery performance | ✅ |
| Onboarding & permissions flow | ✅ |
| Login & account management | ✅ |
| Core features (Filters, Editor, Projects, Settings) | ✅ |
| AI photo generation & processing | ✅ |
| Camera integration & photo upload | ✅ |
| Payment & subscription flows | ✅ |
| Screenshot & media handling | ✅ |
| Cross-platform compatibility (iOS + Android) | ✅ |

---

## Testing Methodology

- **Test type:** Manual functional testing
- **Approach:** Exploratory + structured test cases
- **Coverage:** Functional, usability, compatibility, and performance
- **Bug severity classification:** Low / Medium / High based on user impact
- **Documentation:** Screenshot evidence captured for all findings

---

## Detailed Findings

### 3.1 iOS Setup

**Tested:** App Store search, download, and installation

| Result | Finding |
|---|---|
| ✅ Positive | App found successfully when searching "Glowy AI" |
| ✅ Positive | App downloads without issue |
| ✅ Positive | App icon appears correctly on Home Screen |
| ⚠️ Low | Multiple other apps named "Glowy" exist — discoverability risk |

---

### 3.2 App Store Updates

**Tested:** Version history and update notes visibility

| Result | Finding |
|---|---|
| ✅ Positive | "What's New" section correctly displays version updates |

**Severity:** High — update transparency is important for user trust

---

### 3.3 Storage Capacity

**Tested:** How much storage the app uses

| Result | Finding |
|---|---|
| ✅ Positive | App Store listing shows 271.1 MB |
| ✅ Positive | Actual device usage is 269.5 MB — consistent with listing |

**Severity:** High — storage usage impacts device performance

---

### 3.4 Battery

**Tested:** App functionality at various battery levels (>50%, <20%, <10%)

| Result | Finding |
|---|---|
| ✅ Positive | App functions correctly at all tested battery levels |

**Severity:** High

---

### 3.5 Onboarding Process (Permissions)

**Tested:** Permission requests on app launch

| Result | Finding |
|---|---|
| ✅ Positive | App correctly requests notification permission on first launch |
| ✅ Positive | App correctly requests activity tracking permission |

**Severity:** High — proper permission handling is essential for privacy compliance

---

### 3.6 Login

**Tested:** Account creation and login requirements

| Result | Finding |
|---|---|
| ✅ Positive | App does not require account creation to use the generator |
| ✅ Positive | Core functionality accessible without login |

**Severity:** Low

---

### 3.7 Buttons and Functionality

#### 3.7.1 Filters

- Filters button located bottom left ✅
- PRO upgrade option visible and functional ✅
- Plus button correctly prompts camera or library selection ✅
- 11 subcategories present in correct order ✅
- Credit countdown timer functioning ✅
- All AI Video options require PRO subscription ✅

**Severity:** High

#### 3.7.2 Editor

- Editor accessible from bottom navigation ✅
- Erase Objects, Remove Background, and Photo Editor all functional ✅
- Photo Library permission request handled correctly in both positive and negative scenarios ✅
- **Negative scenario tested:** When permission denied, "Your Photos" button correctly disabled, only Stock Photos accessible ✅
- Text layer customisation (font, colour, orientation) working ✅
- Shape options (Square, Circle, Triangle, Octagon, Heart) all functional ✅
- Canvas size selection by social media format (Facebook, Instagram, etc.) working ✅
- **Bug found:** Support email not visible in iPhone Mail Sent folder after submission

**Severity:** High

#### 3.7.3 Projects

- Previously worked on projects displayed correctly ✅
- Clicking a past project reopens Photo Editor for modification ✅

**Severity:** High

#### 3.7.4 Settings

- "Start 3-Day Free Trial" correctly redirects to payment page ✅
- Rate Us, Support, Change App Icon, Privacy Policy, Terms of Use all functional ✅
- **Bug found:** "Rate Us" page reappears on every app restart — should only show once
- Change App Icon: 4 options available, icon changes correctly upon selection ✅
- Privacy Policy and Terms of Use redirect to correct glowyai.com pages ✅
- App version in Settings matches App Store version ✅

**Severity:** High

---

### 3.8 Payments

**Tested:** PRO subscription flow

| Platform | Weekly | Yearly |
|---|---|---|
| iOS | $9.99 | $39.99 |
| Android | ₺319.99 | ₺1,099.99 |

- Both subscription options clearly displayed ✅
- iOS payment: correctly redirects to App Store double-click confirmation ✅
- Android payment: correctly redirects to Google Play Store ✅
- Privacy Policy, Restore, and Terms of Use visible on payment screen ✅

**Severity:** High — payment flow is critical to app monetisation

---

### 3.9 Screenshots

**Tested:** Screenshot permission behaviour within the app

| Result | Finding |
|---|---|
| ✅ Positive | App allows screenshots — no restrictions imposed |
| ✅ Positive | Screenshots capture edited images correctly |

**Severity:** Medium

---

### 3.10 Android Compatibility

**Tested:** Full app functionality on Android device

- App functions correctly across tested Android versions with no crashes ✅
- UI responsive and consistent with iOS version ✅
- Navigation smooth with no significant delays ✅
- App available and fully functional in Turkish ✅
- Payment flow correctly redirects to Google Play ✅

**Severity:** High

---

## Summary of Issues

| # | Issue | Severity | Impact |
|---|---|---|---|
| 1 | AI tutorial image flow too fast on app restart | Medium | Users cannot process images before proceeding |
| 2 | AI photo generation takes up to 65 seconds per image | **High** | User frustration, decreased engagement |
| 3 | "Rate Us" prompt reappears on every app restart | Medium | Interrupts user experience, especially for returning users |
| 4 | Multiple apps named "Glowy" in App Store | Low | Reduced discoverability, potential incorrect downloads |
| 5 | Support email not visible in iPhone Mail Sent folder | Low | Users may resend unnecessarily, minor UX confusion |

---

## Recommendations

### 1. Optimise AI Photo Processing Speed
**Priority: High**  
Reduce generation time from ~65 seconds to under 30 seconds. Analyse backend processes for optimisation opportunities or allocate additional compute resources. Faster processing is directly tied to user retention.

### 2. Fix "Rate Us" Reappearance
**Priority: Medium**  
Show the Rate Us prompt only once per install. Provide an opt-out option. This prevents frustration for returning users and improves the overall onboarding experience.

### 3. Slow Down Tutorial Image Flow
**Priority: Medium**  
Reduce the speed of AI-generated images shown at app startup. Consider adding a pause option or allowing users to control the pace. This gives users time to appreciate the app's capabilities before proceeding.

### 4. Improve App Store Discoverability
**Priority: Low**  
Differentiate branding from similarly-named apps by adding a unique descriptor to the app title. Optimise App Store keywords and description to improve search ranking.

---

## Conclusion

The Glowy AI application demonstrates strong core functionality with stable performance across both iOS and Android platforms. The primary concern is AI photo generation speed — at up to 65 seconds per image, this creates a significant friction point that directly impacts user satisfaction and engagement.

Secondary issues around the "Rate Us" prompt reappearance and tutorial flow speed are solvable with targeted fixes and would meaningfully improve the experience for returning users.

The payment and subscription flows are functional and reliable across both platforms, which is critical for the app's monetisation model.

With the recommended improvements in place, Glowy AI is well-positioned to deliver a more polished, competitive user experience.

---

## Skills Demonstrated

`Manual Testing` `Mobile QA` `iOS Testing` `Android Testing` `Bug Reporting` `Test Case Design` `Cross-Platform Compatibility` `Severity Classification` `UX Evaluation` `Payment Flow Testing`

---

*Conducted as a freelance QA engagement.*
