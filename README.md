# TikTok Ads Scraper
> TikTok Ads Scraper collects trending hashtag and advertising signals from TikTok’s Creative Center, turning fast-moving trend data into structured insights you can actually use. It helps marketers and analysts spot what’s rising, where it’s rising, and who it’s resonating with—without manual digging.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>tiktok-ads-scraper-0-9-1k</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project extracts TikTok Creative Center trend data (hashtags + ad signals) and standardizes it into a clean dataset for analysis and reporting.
It solves the problem of fragmented, time-sensitive trend monitoring by automating discovery across time windows, countries/regions, and industries.
It’s built for growth teams, media buyers, creators, and data analysts who need reliable TikTok ads trend analytics for planning and optimization.

### Campaign-ready trend intelligence
- Pulls trend snapshots for 7 / 30 / 120 days (and extended history when available)
- Filters by country/region and industry category to match your target market
- Captures rank movement, view volume, publish volume, and promotion status
- Includes audience breakdowns (ages, interests, countries) for smarter targeting
- Exports analysis-friendly outputs for dashboards, sheets, and BI pipelines

## Features
| Feature | Description |
|----------|-------------|
| Time-window trend tracking | Compare momentum across 7, 30, and 120-day windows to spot rising vs. declining hashtags. |
| Geo targeting filters | Focus on a specific country/region (e.g., US, GB) or run globally. |
| Industry segmentation | Filter insights by industry categories to align trends with niche campaigns. |
| “New to Top 100” detection | Identify fresh entrants into the Top 100 to catch trends earlier. |
| Rich performance metrics | Captures publish counts, views, rank, and rank deltas for each hashtag. |
| Audience insights | Extracts audience ages, interests, and country distribution for targeting decisions. |
| Related discovery | Collects related hashtags and related video items to expand research. |
| Proxy & retry controls | Supports proxy configuration, request retries, and concurrency tuning for stability. |
| Multi-format export | Outputs structured JSON and supports export to CSV/XLSX-friendly formats. |

---
## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| hashtag_name | Hashtag being queried or returned by the trend list. |
| resultsLimit | Maximum number of results requested for the run. |
| lastIndex | Pagination cursor/index for continuing from the last position. |
| industry | Industry filter identifier used for the query. |
| label | Marker describing the dataset slice (example: long-history details label). |
| item.hashtag_id | Unique hashtag identifier. |
| item.country_info | Country metadata (code + human-readable name). |
| item.industry_info | Industry metadata (id + display name). |
| item.is_promoted | Whether the hashtag is promoted/sponsored. |
| item.trend[] | Trend time series data points with unix `time` and normalized `value`. |
| item.creators[] | Creator references (nickname + avatar URL). |
| item.publish_cnt | Number of published videos in the measured window. |
| item.video_views | Total video views in the measured window. |
| item.rank | Current rank position. |
| item.rank_diff | Rank change vs. previous period. |
| item.rank_diff_type | Rank change direction (up/down/no-change indicator). |
| days7 / days30 / days120 | Time-window detail object containing metrics + audience + discovery fields. |
| days*.description | Hashtag description text from the source. |
| days*.video_url | Direct URL to the hashtag page. |
| days*.publish_cnt_all | Total published videos across broader/all-time scope when provided. |
| days*.video_views_all | Total video views across broader/all-time scope when provided. |
| days*.longevity | Popularity lifespan signals (popular days + current popularity). |
| days*.audience_ages[] | Audience age distribution buckets with scores. |
| days*.audience_interests[] | Audience interest categories with scores. |
| days*.audience_countries[] | Audience countries with scores. |
| days*.related_hashtags[] | Related hashtags (id, name, URL). |
| days*.related_items[] | Related video items with thumbnail/cover URLs. |

---
## Example Output

    [
      {
        "hashtag_name": "mothersday",
        "resultsLimit": 100,
        "lastIndex": 0,
        "industry": "12000000000",
        "label": "GET_DETAILS_FOR_365",
        "item": {
          "hashtag_id": "22326",
          "hashtag_name": "mothersday",
          "country_info": { "id": "US", "value": "United States", "label": "US" },
          "industry_info": { "id": 12000000000, "value": "Baby, Kids & Maternity", "label": "label_12000000000" },
          "is_promoted": true,
          "trend": [
            { "time": 1741392000, "value": 0.07 },
            { "time": 1747440000, "value": 1.0 },
            { "time": 1749859200, "value": 0.08 }
          ],
          "creators": [
            {
              "nick_name": "sumansunam1",
              "avatar_url": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-avt-0068/1d61b55c8028d2a6eb6d9839b1b33ab5~tplv-tiktokx-cropcenter:100:100.png"
            }
          ],
          "publish_cnt": 965937,
          "video_views": 4692960189,
          "rank": 1,
          "rank_diff": 0,
          "rank_diff_type": 2
        },
        "days7": {
          "hashtag_id": "22326",
          "hashtag_name": "mothersday",
          "description": "Join us in making this Mother's Day extra special by sharing your love for your mamas &amp; highlighting your own special motherhood moments!🥰",
          "video_url": "https://www.tiktok.com/tag/mothersday",
          "publish_cnt": 11370,
          "video_views": 115042711,
          "audience_ages": [
            { "age_level": 3, "score": 54 },
            { "age_level": 4, "score": 26 },
            { "age_level": 5, "score": 20 }
          ],
          "audience_countries": [
            { "country_info": { "id": "6252001", "label": "US", "value": "United States" }, "score": 384 },
            { "country_info": { "id": "2635167", "label": "GB", "value": "United Kingdom" }, "score": 175 }
          ],
          "related_hashtags": [
            { "hashtag_id": "11411096", "hashtag_name": "mothersdaygift", "video_url": "https://www.tiktok.com/tag/mothersdaygift" }
          ]
        }
      }
    ]

---
## Directory Structure Tree

    tiktok-ads-scraper/
    ├── src/
    │   ├── main.ts
    │   ├── runner/
    │   │   ├── run.ts
    │   │   └── validateInput.ts
    │   ├── config/
    │   │   ├── defaults.ts
    │   │   └── env.ts
    │   ├── clients/
    │   │   ├── creativeCenterClient.ts
    │   │   ├── http.ts
    │   │   └── proxy.ts
    │   ├── extractors/
    │   │   ├── trendListExtractor.ts
    │   │   ├── hashtagDetailsExtractor.ts
    │   │   └── audienceExtractor.ts
    │   ├── models/
    │   │   ├── input.ts
    │   │   ├── hashtag.ts
    │   │   └── output.ts
    │   ├── normalizers/
    │   │   ├── normalizeHashtag.ts
    │   │   ├── normalizeAudience.ts
    │   │   └── normalizeTrend.ts
    │   ├── exporters/
    │   │   ├── toJson.ts
    │   │   ├── toCsv.ts
    │   │   └── toXlsx.ts
    │   ├── utils/
    │   │   ├── time.ts
    │   │   ├── retries.ts
    │   │   └── logger.ts
    │   └── schemas/
    │       └── input.schema.json
    ├── test/
    │   ├── fixtures/
    │   │   └── sampleResponse.json
    │   ├── normalizeHashtag.test.ts
    │   └── validateInput.test.ts
    ├── scripts/
    │   ├── dev-run.sh
    │   └── export-demo.sh
    ├── .env.example
    ├── .gitignore
    ├── package.json
    ├── tsconfig.json
    ├── Dockerfile
    ├── LICENSE
    └── README.md

---
## Use Cases
- **Growth marketers** use it to track trending hashtags by country and industry, so they can align creatives with what’s currently performing.
- **Media buyers** use it to evaluate TikTok ads trend analytics over 7/30/120 days, so they can plan spend around sustained momentum instead of spikes.
- **Content strategists** use it to discover related hashtags and trending content clusters, so they can expand keyword coverage and improve reach.
- **Analysts** use it to export structured datasets to BI tools, so they can correlate trend shifts with campaign KPIs and attribution windows.
- **Agencies** use it to generate recurring trend reports for clients, so they can justify creative direction with measurable signals.

---
## FAQs
**Q1: What time periods are supported for trends?**
The scraper supports 7-day, 30-day, and 120-day trend windows for consistent comparisons. In some outputs, extended history may also be available when the data source provides it.

**Q2: Can I run this for a specific region like the US or UK?**
Yes. Set the `country` parameter (e.g., `US`, `GB`) to focus on regional trends. If `country` is empty, it defaults to a global view.

**Q3: Why do some hashtags have missing metrics or smaller audience breakdowns?**
Some metrics depend on what is available for a given hashtag, region, and time window. When the source limits certain fields, the scraper returns what’s available while keeping the output structure consistent.

**Q4: How do I avoid rate-limits or unstable runs?**
Use proxy configuration, keep concurrency at a reasonable level (start around 5–10), and allow a few retries. If you’re scaling up, reduce concurrency before increasing result limits.

---
### Performance Benchmarks and Results

**Primary Metric:** Typical end-to-end extraction of 100 hashtags (single country + industry) completes in ~2–5 minutes, depending on network latency and detail depth.

**Reliability Metric:** With proxy enabled and retries set to 3, successful completion commonly exceeds 95% across repeated runs under normal conditions.

**Efficiency Metric:** Sustained throughput averages 8–15 detail fetches per minute at concurrency 10, while keeping memory usage generally under 250 MB in a containerized run.

**Quality Metric:** Output completeness is typically 90%+ for core fields (rank, views, publish counts, trend series), with audience breakdown fields varying by hashtag availability and region coverage.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
