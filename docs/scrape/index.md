# Web Scraping with the Art of Literary Text Analysis

This is part of the [Art of Literary Text Mining](../) collection. This page is intended to briefly describe how to get started with web scraping, particularly with Juypter Notebooks and the `wget` command.

A very common task when working with text analysis is aquiring a corpus of texts, frequently sourced from the web. Web scraping (or harvesting) is the act of fetching content from the web and extracting relevant content. There are two major kinds of web scraping:

1. fetching the contents from a list of specific URLs
1. fetching as much of web site as possible, often by following links from one page to another (sometimes also called web crawling)

For the first type it's possible to have code that produces a list of URLs to fetch, this is essentially what we did in the [Getting Started](../start/) guide page, especially the Jupyter version using Beautiful Soup. This is a good example of how tools can be mixed and matched in various ways: you could have a Jupyter notebook produce a list of URLs and then provide that list of URLs to Voyant.

## Voyant

![Voyant](../images/voyant48.png) Voyant's web scraping abilities are limited in that it assumes that you'll provide a list of URLs and there's no mechanism for parsing the contents of those URLs in order fetch additional URLs. Still, it can be enormously convenient to paste a list of several URLs and have Voyant construct a corpus from them. Please note that any processing options are applied to all documents as appropriate (for instance, it's not possible to have different HTML CSS Selectors for different URLs, though it is possible to add documents individually by [modifying a corpus](https://voyant-tools.org/docs/#!/guide/modifyingcorpus).

Even if URL fetching in Voyant is convenient, there are times where doing the web scraping outside of Voyant is preferable. One such situation is where you have many URLs, say more than about a dozen. Voyant has to fetch each URL one at a time and that can be time-consuming, which can cause a server timeout. Moreover, if ever an error is encountered you'd need to fetching over from the beginning next time. In fact, we recommend only fetching up to about three URLs at a time.

Another situation is where you need to do some intermediate processing to the documents before analyzing them. In that case, you would scrape (download) them (possibly using techniques described below), edit the documents, and then upload them to Voyant.

## Jupyter Notebook

![Jupyter](../images/jupyter48.png) Our Juypyter notebook will walk through the following steps:

* fetching the contents at http://www.digitalhumanities.org/dhq/index/title.html
* parsing that document to get list of all the articles in the journal
* fetching the contents of each of the article

To continue, please see [Web Scraping](https://nbviewer.jupyter.org/github/sgsinclair/alta/blob/master/ipynb/Scraping.ipynb) with the Art of Literary Text Analysis.

## Wget Command

Web scraping is such a common task that there are dedicated tools for doing it. Web scraping is not only important for people doing text analysis, but also, for instance, to anyone building a web search engine or otherwise wanting to create an archive of a site. One of the most widely used tools is a command-line utility called [`wget`](https://en.m.wikipedia.org/wiki/Wget). Here's a partial list of some of `wget`'s functionality:

* fetch a single page (HTML source only): `wget http://www.digitalhumanities.org/dhq/`
* fetch a single page and its assets: `wget -p -k http://www.digitalhumanities.org/dhq/`
* fetch all URLs listed in the specified file: `wget -i urls.txt`
* fetch a URL and recursively fetch all URLs in the contents: `wget -r http://www.digitalhumanities.org/dhq/`

One of `wget` strengths is in fetching multiple URLs and especially in finding links in one page and following those links to download contents in other pages, and so on recursively. Since `wget` is often used to fetch many URLs it's best to configure it such that is doesn't strain the target server too heavily (by trying to fetch hundreds of URLs as quickly as possible, for instance). A couple of common arguments are added to be a good net citizen (and avoid being blacklisted by servers, which would prevent you from fetching more content).

* `-w`: number of seconds to wait between requests: `wget -w 1 http://www.digitalhumanities.org/dhq/`
* `--limit-rate`: the bandwidth to use in kilobytes/second: `wget --limit-rate=200k http://www.digitalhumanities.org/dhq/`

(Note about arguments: typically one hyphen is used for abbreviations like "w" and two hyphens for full names like "limit-rate".)

A final argument that's useful for our purposes is to tell `wget` to only fetch URLs matching a certain pattern, namely "/dhq/vol/…". We do that with the argument `--accept-regex`

DELETE Another argument is useful for our purposes: `--no-parent` which tells `wget` that the URL is the highest level to fetch [http://www.digitalhumanities.org/dhq/](http://www.digitalhumanities.org/dhq/) and that parent URLs (like [http://www.digitalhumanities.org/](http://www.digitalhumanities.org/) (without /dhq/) should be ignored.

	wget -r --accept-regex "/dhq/vol/" -w 1 --limit-rate 200k http://www.digitalhumanities.org/dhq/

This says "go get the contents of the http://www.digitalhumanities.org/dhq/ recursively (while ignoring any parent URLs), waiting a second between each request and limiting the bandwidth to 200KB/second.

--accept-regex urlregex