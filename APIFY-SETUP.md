# Apify Integration Guide

**Status:** ✅ Connected  
**User:** abdelhak66 (@tigha66)  
**Plan:** FREE ($5/month credits)  
**Token:** Configured at `~/.apify/credentials`  
**Last Updated:** 2026-03-26

---

## Account Summary

| Detail | Value |
|--------|-------|
| **Username** | abdelhaktirha |
| **Email** | abdelhaktirha@gmail.com |
| **Plan** | FREE |
| **Monthly Credits** | $5.00 USD |
| **Max Memory** | 8 GB |
| **Max Concurrent Runs** | 25 |
| **Data Retention** | 7 days |
| **Proxy Groups** | BUYPROXIES94952 (5 proxies) |

---

## Available Actors

### compass/crawler-google-places ✅

**Actor ID:** `nwua9Gu5YrADL7ZDj`  
**Title:** Google Maps Scraper  
**Category:** Lead Generation, Travel  
**Rating:** 4.75/5 (1,043 reviews)  
**Total Runs:** 20.5M+  
**Users:** 324K+

**Description:**
Extract data from thousands of Google Maps locations and businesses, including:
- Reviews & reviewer details
- Images
- Contact info (name, email, job titles)
- Opening hours
- Prices & more

**Pricing (Pay Per Event):**
- Actor start: $0.007 per run
- Place scraped: ~$0.02 per lead

**Free Tier Estimate:**
- $5 credit = ~250 leads/month
- Perfect for testing and small campaigns

---

## API Configuration

### Credentials File
```bash
~/.apify/credentials
```

**Contents:**
```json
{
  "api_token": "[REDACTED]",
  "api_base": "https://api.apify.com/v2"
}
```

**Permissions:** 600 (owner read/write only)

---

## Quick Start

### 1. Run Google Maps Scraper

```bash
curl -X POST \
  "https://api.apify.com/v2/acts/compass~crawler-google-places/runs?token=[REDACTED]" \
  -H "Content-Type: application/json" \
  -d '{
    "searchString": "dentists in Austin, TX",
    "maxCrawledPlaces": 30,
    "proxyConfig": {
      "useApifyProxy": true
    }
  }'
```

### 2. Check Run Status

```bash
curl "https://api.apify.com/v2/actor-runs/{runId}?token=[REDACTED]"
```

### 3. Download Results

```bash
curl "https://api.apify.com/v2/actor-runs/{runId}/dataset/items?token=[REDACTED]" \
  -o leads.csv
```

---

## Integration with Lead Gen Skill

The lead-gen skill automatically uses your configured Apify credentials.

### Example Command
```
Find me 30 dentists in Austin, TX for website redesign outreach
```

### What Happens
1. Lead gen skill reads `~/.apify/credentials`
2. Calls Google Maps Scraper actor
3. Extracts 30 leads with contact info
4. Continues pipeline (crawl → score → draft → output)

---

## Pricing Breakdown

### FREE Plan ($0/month base)
| Resource | Limit |
|----------|-------|
| **Monthly Credits** | $5.00 |
| **Actor Compute Units** | 625/month |
| **Max Memory** | 8 GB |
| **Concurrent Runs** | 25 |
| **Data Retention** | 7 days |
| **Residential Proxy** | 20 GB/month |
| **Google SERP** | 50,000/month |
| **External Transfer** | 1,000 GB/month |

### Cost Per Lead Gen Campaign
```
30 leads campaign:
- Actor start: $0.007
- 30 places × $0.02: $0.60
- Total: ~$0.61

With $5 credit:
- ~8 campaigns/month (240 leads)
- Or 1 large campaign (250 leads)
```

### Upgrade Options
| Plan | Price | Credits | Best For |
|------|-------|---------|----------|
| **FREE** | $0 | $5/mo | Testing, learning |
| **STARTER** | $49 | $49/mo | Small business |
| **SCALE** | $149 | $149/mo | Growing agency |
| **BUSINESS** | $499 | $499/mo | High volume |

---

## Common Use Cases

### 1. Lead Generation Campaign
```json
{
  "searchString": "dentists in Austin, TX",
  "maxCrawledPlaces": 30,
  "proxyConfig": { "useApifyProxy": true }
}
```

### 2. Competitor Research
```json
{
  "searchString": "plumbers near Manchester, UK",
  "maxCrawledPlaces": 50,
  "extractReviews": true,
  "extractImages": true
}
```

### 3. Market Analysis
```json
{
  "searchString": "restaurants in Brooklyn, NY",
  "maxCrawledPlaces": 100,
  "extractOpeningHours": true,
  "extractPriceRange": true
}
```

---

## API Endpoints

### Base URL
```
https://api.apify.com/v2
```

### Key Endpoints

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/acts` | GET | List available actors |
| `/acts/{actorId}` | GET | Get actor details |
| `/acts/{actorId}/runs` | POST | Start actor run |
| `/actor-runs/{runId}` | GET | Get run status |
| `/actor-runs/{runId}/dataset/items` | GET | Download results |
| `/users/me` | GET | Get account info |

---

## Python Example

```python
import requests
import time

API_TOKEN = "[REDACTED]"
ACTOR_ID = "compass~crawler-google-places"

# Start run
response = requests.post(
    f"https://api.apify.com/v2/acts/{ACTOR_ID}/runs?token={API_TOKEN}",
    json={
        "searchString": "dentists in Austin, TX",
        "maxCrawledPlaces": 30,
        "proxyConfig": {"useApifyProxy": True}
    }
)

run_id = response.json()["data"]["id"]
print(f"Run started: {run_id}")

# Wait for completion
while True:
    status = requests.get(
        f"https://api.apify.com/v2/actor-runs/{run_id}?token={API_TOKEN}"
    ).json()["data"]["status"]
    
    if status == "SUCCEEDED":
        break
    elif status == "FAILED":
        print("Run failed!")
        exit(1)
    
    time.sleep(5)

# Download results
results = requests.get(
    f"https://api.apify.com/v2/actor-runs/{run_id}/dataset/items?token={API_TOKEN}"
)

# Save to CSV
with open("leads.csv", "w") as f:
    f.write(results.text)

print(f"Downloaded {len(results.json())} leads")
```

---

## Node.js Example

```javascript
const { ApifyClient } = require('apify-client');

const client = new ApifyClient({
  token: '[REDACTED]',
});

async function scrapeLeads() {
  const runOptions = {
    searchString: 'dentists in Austin, TX',
    maxCrawledPlaces: 30,
    proxyConfig: { useApifyProxy: true },
  };

  // Start actor
  const { id } = await client.actor('compass/crawler-google-places').call(runOptions);

  // Wait for completion
  const { items } = await client.dataset(id).waitForFinish();

  // Download results
  const dataset = await client.dataset(id);
  const leads = await dataset.listItems();

  console.log(`Found ${leads.count} leads`);
  return leads.items;
}

scrapeLeads();
```

---

## Troubleshooting

### "Insufficient credits"
- Check balance: `curl "https://api.apify.com/v2/users/me?token=YOUR_TOKEN"`
- Upgrade plan or wait for monthly reset
- Reduce `maxCrawledPlaces` for smaller campaigns

### "Actor not found"
- Verify actor ID: `compass~crawler-google-places`
- Check actor is public (this one is)
- Try alternative: `apify~google-maps-scraper`

### "Run timed out"
- Increase `timeoutSecs` in run options
- Reduce `maxCrawledPlaces`
- Check proxy configuration

### "No results"
- Wait for run to complete (status: SUCCEEDED)
- Check search string is valid
- Verify location exists on Google Maps

---

## Best Practices

### Cost Optimization
- ✅ Use smallest `maxCrawledPlaces` that meets needs
- ✅ Batch similar searches (one run, multiple queries)
- ✅ Download and backup results within 7 days
- ✅ Cancel failed runs early to save credits

### Data Quality
- ✅ Be specific in search strings
- ✅ Extract emails separately (Hunter/Snov)
- ✅ Verify data before outreach
- ✅ Remove duplicates in post-processing

### Rate Limiting
- ✅ Wait 5-10 seconds between API calls
- ✅ Don't exceed 25 concurrent runs
- ✅ Use webhooks for async workflows
- ✅ Cache results locally

---

## Security

### Token Management
- ✅ Store in `~/.apify/credentials` (mode 600)
- ✅ Never commit to git
- ✅ Rotate if compromised
- ✅ Use environment variables in production

### Access Control
- ✅ FREE plan limits exposure
- ✅ Monitor usage in Apify console
- ✅ Set up usage alerts
- ✅ Review run history regularly

---

## Resources

### Documentation
- **Apify API:** https://docs.apify.com/api/v2
- **Google Maps Scraper:** https://apify.com/compass/crawler-google-places
- **Pricing:** https://apify.com/pricing

### Console
- **Dashboard:** https://console.apify.com
- **Usage:** https://console.apify.com/usage
- **Runs:** https://console.apify.com/actor-runs

### Support
- **Help Center:** https://help.apify.com
- **Community:** https://discord.gg/apify
- **Email:** support@apify.com

---

## Next Steps

### 1. Test Your First Run
```bash
curl -X POST \
  "https://api.apify.com/v2/acts/compass~crawler-google-places/runs?token=[REDACTED]" \
  -H "Content-Type: application/json" \
  -d '{"searchString": "coffee shops in London", "maxCrawledPlaces": 5}'
```

### 2. Integrate with Lead Gen
```
Find me 30 dentists in Austin, TX
```

### 3. Monitor Usage
- Check console.apify.com
- Track credits remaining
- Plan next campaign

---

**Status:** ✅ Ready for lead generation  
**Credits:** $5.00/month (FREE plan)  
**Estimated Leads:** ~250/month  

**Go scrape some leads!** 🎯
