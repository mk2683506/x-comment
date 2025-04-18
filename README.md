tweets = [https://x.com/SoulStrike_EN/status/1911691114316435923]

search_query = f'{query} min_retweets:0 min_faves:{min_likes} lang:"{EN}" since:{since_2025-0414} until:{until_2025-04-17}'

for tweet in sntwitter.TwitterSearchScraper(search_query).get_items():
    # Extract relevant information from the tweet
    tweet_data = {
        "Id": tweet.id,
        "tweet": tweet.content,
        "Likes": tweet.likeCount,
        "Retweets": tweet.retweetCount,
        "Date": tweet.date.strftime("%Y-%m-%d %H:%M:%S"),
        "id": tweet.id,
        "created_at": tweet.date.strftime("%Y-%m-%d %H:%M:%S"),
        "tweet": tweet.rawContent,
        "replies_count": tweet.replyCount,
        "retweets_count": tweet.retweetCount,
        "likes_count": tweet.likeCount,
        "hashtags": tweet.hashtags,
        "cashtags": tweet.cashtags if tweet.cashtags else [],
        "language": tweet.lang,
        "link": tweet.url,
        "conversation_id": tweet.conversationId,
        "Jahr": tweet.date.year,
        "Monat": tweet.date.month,
        "Tag": tweet.date.day,
        "time": tweet.date.time().strftime("%H:%M:%S"),
        "user_id": tweet.user.id,
        "username": tweet.user.username,
    }
    
    tweets.append(tweet_data)
