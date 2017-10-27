# CreepyPasta.org EPUB Generator

This is a script that takes an index url from [creepypasta.org](http://creepypasta.org) and generates an EPUB from the linked stories.

## Usage

```
cp2epub [-ahnostu] [long options...]
        -u STR --url STR     the creepypasta.org url to scrape
        -o STR --output STR  path and filename of final epub to output
        -n INT --count INT   the number of stories to include (includes all
                             by default)
        -s INT --skip INT    skip this many stories from the list
        -t STR --title STR   the title for the ebook
        -a STR --author STR  the author for the ebook
        -h --help            print help message and exit
```

## Example

To get an ebook with the top 5 rated stories in the *Video Games* category, browse to [http://creepypasta.org/creepypasta](http://creepypasta.org/creepypasta), click the *Video Games* tag, then click the *Rating* column header to sort by rating. Copy the url of the resulting page, and then feed that to the script to generate your book:

```
./cp2epub --url "http://www.creepypasta.org/tag/video-games?orderby=highest_rated&order=desc" --count 5 --title "Top 5 Video Game Creepypastas" --output vg_creepypasta_top5.epub
```

The resulting EPUB will contain the top 5 rated stories, one per chapter.

## Prerequisites

It's a perl script and it expects to find both [cURL](https://github.com/curl/curl) and [unfluff](https://github.com/ageitgey/node-unfluff) in your path when you run it.
