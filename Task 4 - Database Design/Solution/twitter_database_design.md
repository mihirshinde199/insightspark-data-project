# 🗃️ Twitter Data Database Design

## 🎯 Objective
Design a scalable and normalized relational database schema to store Twitter data, including original tweets, user replies, quote retweets, and mentions.

---

## 📑 Tables Overview

We will create the following tables:

1. **Users**
2. **Tweets**
3. **Replies**
4. **QuoteRetweets**
5. **Mentions**

---

## 📋 Table Definitions

### 1. `Users`
Stores metadata about each Twitter user.

| Field Name     | Data Type   | Description                       |
|----------------|-------------|-----------------------------------|
| `user_id`      | VARCHAR      | Primary Key - Unique user ID      |
| `username`     | VARCHAR      | Twitter handle                    |
| `display_name` | VARCHAR      | User’s display name               |
| `created_at`   | TIMESTAMP    | Account creation date             |
| `verified`     | BOOLEAN      | Whether user is verified          |

**Primary Key:** `user_id`

---

### 2. `Tweets`
Stores original tweets from users.

| Field Name       | Data Type   | Description                          |
|------------------|-------------|--------------------------------------|
| `tweet_id`       | VARCHAR     | Primary Key - Unique tweet ID        |
| `user_id`        | VARCHAR     | Foreign Key to `Users`               |
| `content`        | TEXT        | Text of the tweet                    |
| `created_at`     | TIMESTAMP   | When the tweet was posted            |
| `retweet_count`  | INT         | Number of retweets                   |
| `like_count`     | INT         | Number of likes                      |

**Primary Key:** `tweet_id`  
**Foreign Key:** `user_id` → `Users.user_id`

---

### 3. `Replies`
Stores replies to tweets.

| Field Name   | Data Type | Description                              |
|--------------|-----------|------------------------------------------|
| `reply_id`   | VARCHAR   | Primary Key - Unique reply tweet ID      |
| `tweet_id`   | VARCHAR   | Foreign Key - Tweet being replied to     |
| `user_id`    | VARCHAR   | Foreign Key - Replier's user ID          |
| `content`    | TEXT      | Text of the reply                        |
| `created_at` | TIMESTAMP | When the reply was posted                |

**Primary Key:** `reply_id`  
**Foreign Keys:**  
- `tweet_id` → `Tweets.tweet_id`  
- `user_id` → `Users.user_id`

---

### 4. `QuoteRetweets`
Stores quote retweets (retweets with a comment).

| Field Name          | Data Type | Description                                 |
|---------------------|-----------|---------------------------------------------|
| `quote_id`          | VARCHAR   | Primary Key - Unique quote retweet ID       |
| `original_tweet_id` | VARCHAR   | Foreign Key - Tweet being quoted            |
| `user_id`           | VARCHAR   | Foreign Key - Quoting user                  |
| `content`           | TEXT      | Comment text added with the retweet         |
| `created_at`        | TIMESTAMP | When the quote retweet was posted           |

**Primary Key:** `quote_id`  
**Foreign Keys:**  
- `original_tweet_id` → `Tweets.tweet_id`  
- `user_id` → `Users.user_id`

---

### 5. `Mentions`
Stores direct mentions within a tweet.

| Field Name         | Data Type | Description                                |
|--------------------|-----------|--------------------------------------------|
| `mention_id`       | VARCHAR   | Primary Key - Unique mention ID            |
| `tweet_id`         | VARCHAR   | Foreign Key - The tweet where mention occurs |
| `mentioned_user_id`| VARCHAR   | Foreign Key - The user being mentioned     |

**Primary Key:** `mention_id`  
**Foreign Keys:**  
- `tweet_id` → `Tweets.tweet_id`  
- `mentioned_user_id` → `Users.user_id`

---

## 🔗 Table Relationships Summary

- One `User` → many `Tweets`, `Replies`, `QuoteRetweets`, and `Mentions`.
- One `Tweet` → many `Replies`, `QuoteRetweets`, and `Mentions`.
- Each table is normalized to **reduce redundancy** and **ensure data integrity**.

---

## ✅ Notes
- All IDs are assumed to match Twitter's unique ID structure (typically large integers or strings).
- `created_at` fields are included to support chronological sorting and timeline building.
- The schema is designed for **scalability**, making it suitable for millions of records.

