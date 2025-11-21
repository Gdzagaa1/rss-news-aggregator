*Programming Paradigms coursework from Stanford's CS107 curriculum.*

See the [assignment PDF](https://github.com/Gdzagaa1/paradigms-04/blob/master/17-Assignment-4-RSS.pdf)  for detailed algorithm explanation and implementation requirements.
# RSS News Feed Aggregator

A C program that builds a searchable index of news articles from RSS feeds, similar to Google News.
This was completed as part of my university coursework at Free University of Tbilisi, following the CS107 curriculum originally developed at Stanford.

## Features

- Downloads and parses RSS feeds from multiple news sources
- Indexes articles by word frequency using custom hash tables
- Interactive search with relevance-based ranking
- Filters common stop words for better search quality
- Prevents duplicate article indexing

## Usage

```bash
# Compile and run
make
./rss-news-search [feeds-file]

# Interactive search
Please enter a single search term [enter to break]: Iraq
We found 196 articles with the word "Iraq"...
```

## Requirements (Linux)

```bash
sudo apt install gcc make libcurl4-openssl-dev:i386 libnsl-dev:i386 gcc-multilib
```

## Data Structures

The program uses three main hash tables:
- **Stop words** - Common words to exclude from indexing
- **Seen articles** - Prevents duplicate article processing  
- **Word index** - Maps words to articles containing them

Each word maps to a vector of articles with frequency counts, sorted by relevance.
