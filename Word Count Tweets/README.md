# Basic Map Reduce Word Count Program

This is a simple implementation of a basic map reduce program using <a href="http://hadoop.apache.org/">Apache™ Hadoop®</a>. 

## Dataset Details
The dataset contained here is extracted and transformed from raw JSON tweets downloaded using Twitter's REST and Streaming API. There are numerous ways to gather tweets. 

### Methods to get Tweets
Some of the options commonly used are listed as follows:
<ol>
<li><a href="https://curl.haxx.se/docs/manpage.html">CURL</a>: Used in command line.
<li><a href="http://www.tweepy.org/">TweePy</a>: A python library for using Twitter APIs.
<li><a href="https://cran.r-project.org/web/packages/twitteR/twitteR.pdf">twitteR</a>: An R library for using Twitter APIs.
</ol>
<br>
There are numerous other ways to download tweets. This is beyond the scope of this program.

### Data
The dataset <a href="https://github.com/InvisibleNemo/MapReduce/blob/master/Word%20Count%20Tweets/tweets.json">tweets.json</a> contains 5000 tweets, which has been extracted using the hashtags <a href="https://twitter.com/search?q=%23S8">#S8</a> and <a href="https://twitter.com/search?q=%23samsung">#samsung</a>.

### Implementation
The <a href="https://github.com/InvisibleNemo/MapReduce/blob/master/Word%20Count%20Tweets/mapJSON.py">mapper</a> and <a href="https://github.com/InvisibleNemo/MapReduce/blob/master/Word%20Count%20Tweets/reduceJSON.py">reducer</a> would be used to perform a word count on the aforementioned dataset. Since, these are python programs the <a href="https://hadoop.apache.org/docs/r1.2.1/streaming.html">Hadoop streaming API</a> is used.

To check the program without using hadoop run the following command in a bash terminal.

```bash
cat tweets.json | python3 mapJSON.py | sort | python3 reduceJSON.py | less
```

