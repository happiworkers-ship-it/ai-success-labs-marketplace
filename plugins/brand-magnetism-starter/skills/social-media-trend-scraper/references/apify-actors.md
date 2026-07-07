# Apify Actor Reference

## Twitter/X Scraper

**Actor ID:** `xquik/x-tweet-scraper`

### Input Schema (key fields)

| Field | Type | Description |
|-------|------|-------------|
| searchTerms | string[] | Search queries (one per topic) |
| maxItems | number | Max tweets to return (default 50, recommend 50 per topic) |
| tweetLanguage | string | Language filter ("en" for English) |
| sort | string | "Top" for engagement-weighted, "Latest" for chronological |

### Output Fields (what you get back)

| Field | Use |
|-------|-----|
| text | The tweet content |
| likeCount | Likes |
| retweetCount | Retweets |
| viewCount | Impressions |
| author.followers | Author's follower count |
| createdAt | When posted |
| author.userName | Handle |
| author.name | Display name |

### Tips
- "Top" sort gives engagement-weighted results — better for trend analysis
- 50 items per topic gives ~200 total across 4 topics, which is plenty
- Add current year to search terms for time-sensitive topics
- Run all topics concurrently to save time

---

## Reddit Scraper

**Actor ID:** `easyapi/reddit-posts-search-scraper`

### Input Schema (key fields)

| Field | Type | Description |
|-------|------|-------------|
| searchTerms | string[] | Search queries |
| maxItems | number | Must be >= 100 (API minimum) |
| sort | string | "relevance" or "hot" or "new" or "top" |
| time | string | "hour", "day", "week", "month", "year", "all" |

### Output Fields

| Field | Use |
|-------|-----|
| title | Post title |
| selftext | Post body text |
| score | Upvotes minus downvotes |
| num_comments | Comment count |
| subreddit | Which community |
| created_utc | When posted |
| author | Username |

### Known Issues
- Can be slow (2+ minutes per scrape)
- May hit memory limits (8GB) on broad searches
- Sometimes times out entirely
- **Recommendation:** Always run async and don't block the workflow waiting for Reddit results. Twitter data alone is sufficient for trend analysis.

---

## Execution Strategy

1. Launch all Twitter scrapes first (they're fast — usually under 60 seconds)
2. Optionally launch Reddit scrapes in parallel
3. Collect Twitter results as they complete
4. If Reddit finishes in time, include it; if not, proceed without it
5. Never let Reddit scraper failures block delivery of the final report
