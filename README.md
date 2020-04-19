# Analysis of John Mayer's Lyrics

Every artist goes through changes in life and their music usually reflects that. I'm a big fan of John Mayer's music, mostly because he's one of the few artists that are keeping the guitar solo alive in modern music. Being a big guitar fan I often get distracted and lost in the guitar solos and background music. But the music aspect aside I was curious to learn what John Mayer sings about through his lyrics and find out: 
1. Changes in vocablury across his albums
2. The general sentiment of his lyrics (did they have a positive tone or a negative tone)
3. What topics did he sing about

I've broken down this project into 4 main steps

1. [**Create the Data Sets**](<1 - Data Collection & EDA - John-Mayer-Lyrics-Analysis.ipynb>)
    1. Use BeutifulSoup and Genius.com API to get Lyrics
    2. Clean and prepare the Data 
    3. Convert the data into required formats (Corpus and Document-Term-Matrix)


2. [**EDA (Explarotary Data Analysis)**](<1 - Data Collection & EDA - John-Mayer-Lyrics-Analysis.ipynb>)
    1. Most common words
    2. Wordclouds
    3. Lexical Richness of Each Album


3. [**Sentiment Analysis**](<2 - Sentiment Analysis - JM Lyrics Analysis.ipynb>)
    1. Subjectivity and Polarity of each Album
    2. Changes in Polarity over the years(Albums)
    3. Changes in Polarity in each Album
    4. Comparison of the above results


4. [**Topic Modeling**](<3 - Topic Modeling - JM Lyrics Analysis.ipynb>)
    1. Using LDA (Latent Derilicht Analysis) and NMF (Non-negative Matrix factorization) to identify common topics within songs/albums
    
# Summary of Findings

Below is just a summary of the analysis and visualizations. For more detailed explanations of the techniques and steps performed, please refer to the actual jupyter notebooks themselves.

## Preliminary EDA

### Word Clouds

Once the lyrics were extracted and cleaned by removing punctuation, quotes, stop words, etc. After accounting for common words, I analysed the lyrics on a album level. Using a word cloud I was able to get a rough idea of what words were prominent in each album.

![WordCloud](/images/wordClouds2.png)

### Lexical Richness across Albums

The number of unique words divided by the number of words give us the richness in vocablury of each album.


![LexicalRichness](/images/LexicalRichness.png)

## Sentiment Analysis

I used the textblob module to carry out sentiment analysis. There are two different measures, polarity and subjectivity

* **Polarity**: How positive or negative a word is. -1 is very negative. 0 is neutral and +1 is very positive.
* **Subjectivity**: How subjective, or opinionated a word is. 0 is objective(facts). +1 is very much subjective (an opinion and has more personal views/feelings/opinions).

![SentimentGeneral](/images/sentimentGeneral.png)


### Change in Polarity Accross the Years

This plot shows how the polarity changed over the years. Seems like the polarity is usually alternating up and down. Except in 2012 and 2013, the albums come in quick succession and it's an increase in polarity.

![PolarityAlbumTrend](/images/polarityGeneralTrend.png)


### Change in Polarity Within each Album

I was interested to see if there was any pattern in how the plarity changed through the tracks in each album. Things like, does he start negative and end positive or vice versa, is there a story in there?

We can see that his songs vary in levels in polarity frequently between positive and negative polarity. The takeaway is that the lyrics definitely do not have the same mood. Which supports my knowledge about his songs. Some are about heartbreak, some are more upbeat and happier.

His albums are overall positive, but Heavier Things and Battle Studies seem to be the 'heaviest'(lowest polarity). Paradise valley seems to be the most positive album.


![PolaritySubplot](/images/polaritySubplot.png)


## Topic Modeling

Topic modeling is the process of identifying topics in a set of documents. I used LDA (Latent Derilicht Analysis) and NMF (Non-negative Matrix factorization) to identify common topics within songs/albums. Both of these are unsupervised algorithms, which means that the actual topics should be identified by the user based on the words in each topic. 

There is some art and fine tuning involved with topic modeling. I could definitely spend more time to refine the results. Based on what I have for now, three topics that I identified were:

    1.  Family (Mothers and Daughters)
    2.  Living Life
    3.  Breakups

### LDA Output Used to Derive Topics

```
[(0,
  '0.022*"world" + 0.014*"sadness" + 0.013*"baby" + 0.013*"bold" + 0.012*"bed" + 0.011*"repair" + 0.010*"yeah" + 0.010*"daughters" + 0.009*"mothers" + 0.008*"someday"'),
 (1,
  '0.027*"whiskey" + 0.016*"water" + 0.014*"face" + 0.014*"olivia" + 0.013*"aint" + 0.011*"boy" + 0.011*"age" + 0.010*"days" + 0.008*"free" + 0.008*"worry"'),
 (2,
  '0.016*"half" + 0.013*"goodbye" + 0.010*"long" + 0.008*"night" + 0.008*"neon" + 0.008*"helpless" + 0.008*"heartbreak" + 0.007*"hearts" + 0.007*"gon" + 0.007*"body"')]
```

## Conclusion

Even though this was a very open ended project, I managed to learn a bunch of different techniques and practice visualizations. 

It seems like his music varies between both low and higher polarity. It might be related to changes in his personal life. Within each album though, the polarity changes, frequently switching between happy/sad songs.

The albums with the lowest polarity (albums with the most negarive lyrics) are Heavier Things and Battle Studies.
The most positive album seems to be Paradise Valley.

The three main topics that he sings about seem to be Family, Living Life and Breakups (that's no surprise with most artists is it?)

There are a lot of additional steps that can be done that I just didn't have the time to. 
It would also be interesting to see 
* How these findings match with the music in each song/album
* Do a similar analysis with other artists and compare how his lyrics are in terms of sentiment and polarity to other similar artists
