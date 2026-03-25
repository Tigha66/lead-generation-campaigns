# Lead Gen Skill - Quick Start Guide

**Status:** ✅ Installed  
**Location:** `/home/admin/.openclaw/workspace/skills/lead-gen/SKILL.md`  
**Compliance:** CAN-SPAM + TCPA compliant (US)

---

## 🚀 Quick Start

### Basic Command
```
Find me 30 dentists in Austin, TX for website redesign outreach
```

### What Happens
1. **Scrapes** Google Places for 30 dentists
2. **Crawls** each website for emails + contact info
3. **Scores** each lead (1-10 opportunity score)
4. **Drafts** personalized outreach emails
5. **Outputs** CSV to your Desktop + Gmail drafts

---

## 📋 Required Info

Before running, collect from user:

| Field | Example | Required |
|-------|---------|----------|
| **Business Type** | "dentists", "HVAC companies", "estate agents" | ✅ |
| **Location** | "Austin, TX", "London, UK", "Melbourne" | ✅ |
| **Count** | 10-100 (default: 30) | ✅ |
| **Outreach Angle** | "website redesign", "lead generation", "SEO" | ✅ |

---

## 🎯 Example Commands

### Website Redesign Campaign
```
Find me 50 nail salons in London with poor websites for redesign outreach
```

### Lead Generation Service
```
Generate 30 HVAC companies in Phoenix, AZ for lead gen service pitch
```

### SEO Audit Campaign
```
Find 25 estate agents in Manchester for SEO audit outreach
```

### Local Business Focus
```
Scrape 20 restaurants in Brooklyn, NY for marketing outreach
```

---

## 📊 Output Files

### CSV File
**Location:** `~/Desktop/leads-[type]-[location]-[date].csv`

**Columns:**
| Column | Description |
|--------|-------------|
| `company_name` | Business name |
| `rating` | Google rating (1-5) |
| `reviews` | Review count |
| `email` | Email or "No email on site" |
| `phone` | Phone number |
| `website` | Website URL |
| `address` | Full address |
| `opportunity_score` | 1-10 score |
| `gaps` | Missing features |
| `outreach_draft` | Email/message draft |
| `contact_method` | "email" or "contact_form" |

### Gmail Drafts
- **Saved for:** Leads with emails
- **Location:** `[Gmail]/Drafts`
- **Prefix:** `[HIGH]`, `[MED]`, `[LOW]` by priority

---

## 🎯 Opportunity Scoring

### Score Breakdown
| Score | Priority | Action |
|-------|----------|--------|
| **8-10** | 🔴 High | Immediate personalized outreach |
| **6-7** | 🟡 Medium | Standard outreach |
| **4-5** | 🟢 Low | Batch/template outreach |
| **1-3** | ⚪ Skip | Not qualified |

### Scoring Factors
- Website quality (30%)
- Email visibility (20%)
- Online presence/ratings (20%)
- Tech gaps (20%)
- Competitive gap (10%)

---

## 📧 Email Templates Included

### Template 1: Website Redesign
```
Subject: Quick question about [company]'s website

Hi [Name],

I noticed [specific observation from their site]...

[Personalized hook about their rating/reviews]

I specialize in [what you sell] and recently helped [similar business]...

Worth a quick chat?

Best,
[Your Name]
[Unsubscribe option]
```

### Template 2: Lead Generation
```
Subject: [company] + more qualified leads

Hi [Name],

I noticed [observation about their online presence]...

We help [business type] achieve [result]...

Recent result: [similar company case study]...

Interested?

Best,
[Your Name]
```

### Template 3: Contact Form (Short)
```
Subject: Partnership opportunity

Hi [company] team,

I was impressed by [specific positive observation]...

I help businesses like yours [value prop]...

Are you the right person to speak with?

Thanks,
[Your Name]
```

---

## ⚖️ Compliance Checklist

### Before Sending
- [ ] B2B only (business emails, not Gmail/Yahoo)
- [ ] Real identity in signature
- [ ] Physical address included
- [ ] Unsubscribe option included
- [ ] Subject line is accurate
- [ ] No misleading claims

### CAN-SPAM Requirements
✅ Accurate headers  
✅ Non-deceptive subject  
✅ Clear disclosure (advertisement)  
✅ Physical address  
✅ Unsubscribe mechanism  
✅ Honor opt-outs within 10 days  

### TCPA Rules
❌ No mass texting without consent  
❌ No auto-dialers without permission  
✅ Manual calls to business landlines OK  
✅ Contact forms OK  

**Full compliance guide:** `~/leads/COMPLIANCE-GUIDE.md`

---

## 🛠️ Tools Used

| Tool | Purpose | Cost |
|------|---------|------|
| **Apify** | Google Places scraping | Free: 250/mo |
| **web_fetch** | Website crawling | Free |
| **web_search** | Enrichment | Free |
| **Himalaya** | Gmail drafts | Free |
| **here.now** | Report hosting | Free |

### Alternatives
- **Outscraper** — 500 free leads
- **Hunter.io** — 25 free emails/mo
- **Snov.io** — 50 free verifications/mo

---

## 📈 Expected Results

### For 30 Leads
| Metric | Expected |
|--------|----------|
| With website | 25-28 (85-93%) |
| With email | 18-24 (60-80%) |
| Contact form only | 4-8 (15-25%) |
| No contact info | 1-3 (5-10%) |

### Outreach Performance
| Metric | Target |
|--------|--------|
| Email → Reply | 5-15% |
| Reply → Call | 20-40% |
| Call → Close | 10-30% |
| **Cost per lead** | <$0.50 |
| **Cost per client** | <$100 |

---

## 🔄 Follow-Up Sequence

| Day | Action | Template |
|-----|--------|----------|
| **Day 0** | Initial email | Main template |
| **Day 3** | Follow-up #1 | "Bumping this up..." |
| **Day 7** | Follow-up #2 | "Last try..." |
| **Day 14** | Breakup | "Closing the file..." |

---

## 💡 Best Practices

### Personalization
- ✅ Reference their rating/reviews
- ✅ Mention specific website elements
- ✅ Note years in business
- ✅ Compare to local competitors

### Efficiency
- ✅ Batch similar tasks
- ✅ Use templates but personalize first 2 sentences
- ✅ Prioritize high-score leads (8+)
- ✅ Set up Gmail filters for responses

### Quality Control
- ✅ Verify emails before sending
- ✅ Check websites are live
- ✅ Test all links in drafts
- ✅ Review CSV before sending

---

## 📁 File Structure

```
/home/admin/.openclaw/workspace/
├── skills/
│   └── lead-gen/
│       └── SKILL.md          # Main skill file
├── leads/
│   ├── COMPLIANCE-GUIDE.md   # Legal reference
│   └── QUICK-START.md        # This file
└── Desktop/
    └── leads-[type]-[location]-[date].csv  # Output
```

---

## 🎬 Example Workflow

### User Request
```
"Find me 30 dentists in Austin, TX for website redesign outreach"
```

### Execution Flow
```
1. SCRAPE (Apify)
   └─> 30 dentists from Google Places
   └─> Extract: name, phone, website, rating, reviews

2. CRAWL (web_fetch)
   └─> Fetch homepage + contact page for each
   └─> Find: emails, forms, gaps

3. SCORE (1-10)
   └─> Calculate opportunity score
   └─> Identify personalization angles

4. DRAFT (Emails)
   └─> Write personalized outreach
   └─> Include compliance elements

5. OUTPUT
   └─> CSV to Desktop
   └─> Gmail drafts saved
   └─> Summary report
```

### Sample Summary
```
📊 Lead Generation Report

Business Type: Dentists
Location: Austin, TX
Date: 2026-03-26

Results:
- Total scraped: 30
- With website: 28 (93%)
- With email: 22 (73%)
- Contact form only: 6 (20%)

Opportunity Scores:
- High (8-10): 8 leads 🔴
- Medium (6-7): 12 leads 🟡
- Low (4-5): 7 leads 🟢

Output:
- CSV: ~/Desktop/leads-dentists-austin-tx-2026-03-26.csv
- Gmail Drafts: 22 saved
```

---

## ⚠️ Troubleshooting

### "No emails found"
- Check contact page specifically
- Search for `mailto:` links
- Try `web_search "[business name] email"`

### "Apify quota exceeded"
- Wait for monthly reset
- Use Outscraper alternative (500 free)
- Manual Google Maps compilation

### "Gmail draft not saving"
- Verify Himalaya: `himalaya account list`
- Check folder: `himalaya folder list`
- Save manually in Gmail web

### "Website not loading"
- Try HTTP vs HTTPS
- Check if site is down
- Note as opportunity signal

---

## 📞 Support Resources

### Documentation
- **Main Skill:** `skills/lead-gen/SKILL.md`
- **Compliance:** `leads/COMPLIANCE-GUIDE.md`
- **Quick Start:** This file

### External
- **FTC CAN-SPAM:** https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business
- **DNC Registry:** https://www.donotcall.gov
- **Apify Docs:** https://docs.apify.com

---

## 🎯 Next Steps

1. **Run your first campaign**
   ```
   Find me 30 [business type] in [location] for [offer] outreach
   ```

2. **Review the CSV output**
   - Check opportunity scores
   - Prioritize high-score leads (8-10)

3. **Send from Gmail drafts**
   - Review and customize each draft
   - Send in batches (10-20/day)

4. **Track responses**
   - Mark replies in CSV
   - Book calls with interested leads

5. **Iterate**
   - Adjust templates based on reply rates
   - Refine targeting for next campaign

---

**Ready to generate leads?** Just say:

> "Find me 30 [business type] in [location] for [your offer]"

---

**Created:** 2026-03-26  
**Version:** 1.0  
**Status:** Production Ready
