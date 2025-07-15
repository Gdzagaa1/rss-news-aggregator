[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/36XIBlW7)
## დავალების ატვირთვა
დავალება უნდა ატვირთოთ თქვენს პერსონალურ Github Classroom-ის რეპოზიტორიაში.

## საჭირო პაკეტები
დაგჭირდებათ libcurl პაკეტის დაყენება
```sh
dpkg --add-architecture i386
apt update
apt install gcc make
apt install libcurl4-openssl-dev:i386
apt install libnsl-dev:i386
apt install gcc-multilib
```

## კომპილაცია
```sh
make
```

## ტესტებისთვის საჭირო data ფაილები
`make` ის პირველი გაშვება ავტომატურად შექმნის data დირექტორიას ტესტებისთვის საჭირო ფაილებით.  
თუ რატომღაც ეს ფაილები "დაგიზიანდათ", მათი თავიდან ჩამოტვირთვისთვის გაუშვით:
```sh
rm -rf data/
make data
```

## ტესტირება
```sh
./assn-4-checker-64 ./rss-news-search
./assn-4-checker-64 ./rss-news-search -m
```






# RSS News Feed Aggregator
*Programming Paradigms course project*

A C program that builds a searchable index of news articles from RSS feeds, similar to Google News.

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

## Documentation

See the assignment PDF for detailed algorithm explanation and implementation requirements.