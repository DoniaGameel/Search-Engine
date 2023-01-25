# Search-Engine

## Search Engine Modules:

## 1-Web Crawler:

The web crawler is a software agent that collects documents from the web. The crawler starts with a list of URL
addresses (seed set). It downloads the documents identified by these URLs and extracts hyper-links from them.
The extracted URLs are added to the list of URLs to be downloaded. Thus, web crawling is a recursive process.

**Number of Crawled pages is 5000 pages**

**multithreaded crawler implementation where the user can control the number of threads
before starting the crawler.**

**The crawler can maintain its state so that it can, if interrupted, be started again to crawl the documents
on the list without revisiting documents that have been previously downloaded.**

**The crawler can only crawl HTML documents**

**The crawler does not visit the same PAGE more than once.By normalizimg URLs and check if they are
referring to the same page.**


## 2-Indexer:

The output of web crawling process is a set of downloaded HTML documents. To respond to user queries fast
enough, the contents of these documents have to be indexed in a data structure that stores the words
contained in each document and their importance (e.g., whether they are in the title, in a header or in plain
text).This data structure has to satisfy the following properties:

● **_Persistence_: The index has to be maintained in secondary storage. You can implement your own file
structure or use a database.**

● **_Fast Retrieval_: The index must be optimized for responding to queries like: The set of documents containing a specific word (or set of words)**

● **_Incremental Update_: It must be possible to update an existing index with a set of newly crawled HTML documents.**

## 3-Query Processor

This module receives search queries, performs necessary preprocessing and searches the index for relevant
documents. Retrieve documents containing words that share the same stem with those in the search query.
For example, the search query “travel” should match (with lower degree) the words “traveler”, “traveling” ... etc.

## 4-Phrase Searching

Search engines will generally search for words as phrases when quotation marks are placed around the
phrase.

## 5-Ranker

The ranker module sorts documents based on their popularity and relevance to the search query.

**A. _Relevance*_*

Relevance is a relation between the query words and the result page and could be calculated in several
ways such as tf-idf of the query word in the result page or simply whether the query word appeared in
the title, heading, or body. And then you aggregate the scores from all query words to produce the final
page relevance score.

**B._ Popularity_**

Popularity is a measure for the importance of any web page regardless the requested query. You can
use pagerank algorithm (as explained in the lecture) or other ranking algorithms to calculate each page
popularity.

## 6-Web Interface

● This interface receives user queries and displays the resulting pages returned by the engine

● The result appears with snippets of the text containing queries words.

## How to run the project?

1-Run CrawlerMain file0

2-Run Index file

3-Run InterfaceHandler file

4-Make sure that tomcat server is open

5-Open your browser and search for: localhost:8080/searchPage.html
