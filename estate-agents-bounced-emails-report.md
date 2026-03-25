# ❌ BOUNCED EMAILS - DO NOT USE

**Date:** 2026-03-23  
**Issue:** 14 out of 21 estate agent emails bounced with "Address not found"  
**Root Cause:** Email patterns were assumed/guessed without verification

---

## Bounced Email Addresses (INVALID - Do Not Use)

| # | Company | Bounced Email | Status |
|---|---------|---------------|--------|
| 1 | Anchored Properties | info@anchoredproperties.co.uk | ❌ Bounced |
| 2 | Aston Chase | info@astonchase.co.uk | ❌ Bounced |
| 3 | Aston Chase King's Cross | kingscross@astonchase.co.uk | ❌ Bounced |
| 4 | Douglas & Gordon Belgravia | belgravia@douglasandgordon.com | ❌ Bounced |
| 5 | Douglas & Gordon Chelsea | chelsea@douglasandgordon.com | ❌ Bounced |
| 6 | Douglas & Gordon Notting Hill | nottinghill@douglasandgordon.com | ❌ Bounced |
| 7 | Chestertons Belgravia | belgravia@chestertons.co.uk | ❌ Bounced |
| 8 | Linley & Simpson Leeds | leeds@linleyandsimpson.co.uk | ❌ Bounced |
| 9 | Rettie & Co Edinburgh | edinburgh@rettie.co.uk | ❌ Bounced |
| 10 | Brand Vaughan Brighton | brighton@brandvaughan.co.uk | ❌ Bounced |
| 11 | Henry Adams Portsmouth | portsmouth@henryadams.co.uk | ❌ Bounced |
| 12 | Move Residential Liverpool | liverpool@moveresidential.co.uk | ❌ Bounced |
| 13 | Gascoigne Halman Manchester | manchester@gascoignehalman.co.uk | ❌ Bounced |
| 14 | Sanderson Young Newcastle | newcastle@sandersonyoung.co.uk | ❌ Bounced |

---

## ✅ Emails That Delivered Successfully

| # | Company | Email | Status |
|---|---------|-------|--------|
| 1 | Acorn Property Bristol | bristol@acornproperty.com | ✅ Delivered |
| 2 | Acorn Property Bath | bath@acornproperty.com | ✅ Delivered |
| 3 | Cheffins Cambridge | cambridge@cheffins.co.uk | ✅ Delivered |
| 4 | Manning Stainton Leeds | leeds@manningstainton.co.uk | ✅ Delivered |
| 5 | Pacitti Jones Glasgow | glasgow@pacittijones.com | ✅ Delivered |
| 6 | Mishon Mackay Brighton | brighton@mishonmackay.com | ✅ Delivered |
| 7 | Independent London | hello@independentlondon.net | ✅ Delivered (sent earlier) |
| 8 | Portico Highbury | highbury.sales@portico.com | ✅ Delivered (sent earlier) |
| 9 | Maguire Jackson | bham@maguirejackson.com | ✅ Delivered (sent earlier) |
| 10 | LV Property | Hello@lvproperty.co.uk | ✅ Delivered (sent earlier) |

---

## Next Steps

### Option 1: Manual Verification (Recommended)
Visit each company's official website and find their contact page:

1. **Anchored Properties** → anchoredproperties.co.uk/contact
2. **Aston Chase** → astonchase.co.uk/contact
3. **Douglas & Gordon** → douglasandgordon.com/contact-us
4. **Chestertons** → chestertons.co.uk/contact
5. **Linley & Simpson** → linleyandsimpson.co.uk/contact
6. **Rettie & Co** → rettie.co.uk/contact
7. **Brand Vaughan** → brandvaughan.co.uk/contact
8. **Henry Adams** → henryadams.co.uk/contact
9. **Move Residential** → moveresidential.co.uk/contact
10. **Gascoigne Halman** → gascoignehalman.co.uk/contact
11. **Sanderson Young** → sandersonyoung.co.uk/contact

### Option 2: Use Generic Contact Forms
Most agency websites have contact forms that bypass email guessing entirely.

### Option 3: Phone First
Call reception and ask for the correct email address for sales/lettings enquiries.

---

## Lesson Learned

**NEVER assume email patterns.** Always verify via:
- Official website contact page
- LinkedIn company page
- Rightmove/Zoopla agent profile
- Phone call to reception

**Valid patterns that worked:**
- `branch@acornproperty.com` ✅
- `city@cheffins.co.uk` ✅
- `city@manningstainton.co.uk` ✅
- `city@pacittijones.com` ✅
- `city@mishonmackay.com` ✅

**Invalid patterns (failed):**
- `info@company.co.uk` ❌ (often goes to web host, not agency)
- `branch@douglasandgordon.com` ❌ (they use different format)
- `branch@chestertons.co.uk` ❌ (they use different format)

---

## Corrected Action Plan

1. **Pause** - Don't send more emails until verified
2. **Verify** - Manually check websites for correct contact emails
3. **Update** - Create new CSV with verified emails only
4. **Resend** - Send to verified addresses with apology/follow-up
5. **Track** - Monitor bounce rate (should be &lt;2% with verified emails)
