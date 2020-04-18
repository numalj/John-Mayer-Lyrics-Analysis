# Analysis of John Mayer's Lyrics

Every artist goes through changes in life and their music usually reflects that. I'm a big fan of John Mayer's music, mostly because he's one of the few artists that are keeping the guitar solo alive in modern music. Being a big guitar fan I often get distracted and lost in the guitar solos and background music. But the music aspect aside I was curious to learn what John Mayer sings about through his lyrics and find out: 
1. Changes in vocablury across his albums
2. The general sentiment of his lyrics (did they have a positive tone or a negative tone)
3. What topics did he sing about

I've broken down this project into 4 main steps

1. **Create the Data Sets**
    1. Use BeutifulSoup and Genius.com API to get Lyrics
    2. Clean and prepare the Data 
    3. Convert the data into required formats (Corpus and Document-Term-Matrix)


2. **EDA (Explarotary Data Analysis)**
    1. Most common words
    2. Wordclouds
    3. Lexical Richness of Each Album


3. **Sentiment Analysis**
    1. Subjectivity and Polarity of each Album
    2. Changes in Polarity over the years(Albums)
    3. Changes in Polarity in each Album
    4. Comparison of the above results


4. **Topic Modeling**
    1. Using LDA (Latent Derilicht Analysis) and NMF (Non-negative Matrix factorization) to identify common topics within songs/albums
    
# Findings


## Preliminary EDA
Once the lyrics were extracted and cleaned by removing punctuation, quotes, stop words, etc. After accounting for common words, I analysed the lyrics on a album level. Using a word cloud I was able to get a rough idea of what words were prominent in each album.

![WordCloud](/images/wordCloud2.png)

