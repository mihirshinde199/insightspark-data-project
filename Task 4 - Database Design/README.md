# 🔹 Task 4: Twitter Data Database Design

## 🔢 Objective
Design a normalized relational database schema to store tweet data, including replies, quote retweets, and mentions, for InsightSpark's future analytical use.

## 📁 Files
- `twitter_database_design.md` — This document (table schema proposal)

## 📊 Tables & Fields

### Tweets
- `tweet_id` (PK): Unique tweet ID
- `user_id` (FK): Author of the tweet
- `content`: Tweet text
- `created_at`: Timestamp
- `retweet_count`, `like_count`

### Users
- `user_id` (PK): Unique user ID
- `username`, `display_name`, `created_at`, `verified`

### Replies
- `reply_id` (PK): Unique reply tweet ID
- `tweet_id` (FK): Original tweet
- `user_id` (FK): Replier
- `content`, `created_at`

### QuoteRetweets
- `quote_id` (PK): Quote tweet ID
- `original_tweet_id` (FK): Tweet being quoted
- `user_id` (FK): Quoting user
- `content`, `created_at`

### Mentions
- `mention_id` (PK): ID for mention event
- `tweet_id` (FK): Tweet containing the mention
- `mentioned_user_id` (FK): User being mentioned

## 🔗 Relationships
- One `User` can have many `Tweets`, `Replies`, `QuoteRetweets`
- Each `Reply` or `QuoteRetweet` is tied to one `Tweet`
- Mentions link a tweet to the user being referenced

---

> This task highlights the candidate's understanding of normalized schema design, relational integrity, and scalable data storage for dynamic social media content.
