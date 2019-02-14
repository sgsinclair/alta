# Collocates with the Art of Literary Text Mining

In the previous meta-guide we considered the nature of bits and bytes and strings and how we might fruitfully [count occurrences](../count/). This page shifts focus from finding and counting terms to considering the lexical context of terms. In other words, if we were to collect the terms that are in proximity to our keyword, what might we observe?

## Concordances

Concordances are a very old "technology" or technique, reaching back at least to the 12the Century when theologians sought to better understand certain concepts by creating a type of extended index of the occurrences of terms. Even though concordances pre-date the computer by centuries, the digital makes it far easier to re-organize data. Imagine we have the following excerpt from Ursula LeGuin's _The Left Hand of Darkness_:

	Insofar as I love life, I love the hills of the Domain of Estre, but that sort of love does not have a boundary-line of hate. And beyond that, I am ignorant, I hope.

This is one text, but now let's imagine that we want to generate a concordance where the keyword is "love", in other words, each occurrence of "love" with some context (three words) on each side:

	Insofar as I **love** life, I love
	love life, I **love** the hills of
	that sort of **love** does not have

This, in certain ways, is a new text and we can consider it as such for counting – what are the top frequency terms in this new text? Our counting now has an additional layer of potential meaning: we are now focusing on terms that are related to our keyword. High frequency terms in this new text may be said to be related to the keywords, they seem to tend to occur together (as always, it's probably more useful if we remove the stopwords. In fact, our concordance might be more useful already if we skip stopwords:

	**love** life, love hills
	love life **love** hills Domain Estre
	hills Domain Estre **love** boundary-line hate ignorant

This example demonstrates one of the possible dangers of simple concordancing: because of the proximity of two occurrences of "love" some of the same words are duplicated. We could resolve this with some additional coding, but in most cases, depending on the term of interest and the size of the context, it's rarely a problem.

## Collocates

Collocates (we see co-located here) are terms that appear in some pre-defined proximity. At some levels any two terms in a text are collocates (this is sometimes referred to bag-of-words where all words are considered together regardless of position). But usually collocates are considered in a smaller window (often single-digit terms in each direction).

What do collocates tell us? In many cases probably not much. In novels we often see "he said" or "she said" so we'd expect "said" to have as high collocates "he" and "she" (likewise, "he" and "she" might have as an important collocate "said"). In practice "he" and "she" (and possibly "said") may be hidden from view because of a stoplist.

## Collocates in Voyant

![Voyant](../images/voyant48.png) Voyant has several tools that use collocate information.

### Links 

<iframe src="https://voyant-tools.org/tool/CollocatesGraph/?corpus=austen" style="width: 375px; height: 350px; float: right;"></iframe> A first collocates-based tool is _Links_ (shown on the right), which is in the tab of the upper left-hand tool panel (where Cirrus is shown by default). When first opened _Links_ selects three of the highest frequency terms (shown in blue boxes) and then fetches collocates of those terms (shown in the orange boxes).

A line between two terms indicates a collocate relationship, in other words, those two terms occur together more often. The thicker the line, the more frequent (relative to all collocate links shown) the collocation. This is a relatively complex visualization between it's showing multiple things including:

* highest frequency terms
* collocates of those high frequency terms, indicated with lines
* other collocate relationships indicated by lines (such as between orange boxes)

This is a network graph in that it's showing the various relationships (by virtue of collocation) of both keywords and collocate words in the text. The trick is knowing the extent to which a connection between two words is more coincidental or more indicative of a potentially significant relationship.

It's worth noting that when you click on a term in the _Links_ tool that term will likely appear in other tools, such as the _Reader_ and _Trends_. You can also click on the lines in _Links_ to initiate a search of when the two terms at the ends of the line occur in proximity, this is a proximity search.

For instance, I can delete the current terms in _Links_ (see the button near the bottom of the tool) and add the term "love" to the screen by searching and selecting it in the textbox. I can click on the term "love" multiple times to fetch additional occurrences. Then I can choose one of the collocates by clicking a the line that separates two terms of interest, such as "love" and "young".

<iframe src="https://voyant-tools.org/tool/CollocatesGraph/?corpus=austen&query=love&mode=corpus&centralize=love" style="width: 375px; height: 350px; float: right;"></iframe> Although I can click on a word to fetch more collocates, sometimes it's useful to see many more collocates at once. That's possible in _Links_ for one keyword at a time: right-click or Ctrl-click on a term and select _Centralize_ from the menu that appears. That will place the keyword in the middle and show all the collocates that have been fetched (to some limit), ordered by frequency, in the periphery. To revert to the previous mode, right/ctrl-click and choose _Fetch Collocates_ from the menu.

### TermsBerry

<iframe src="https://voyant-tools.org/tool/TermsBerry/?corpus=austen" style="width: 375px; height: 350px; float: left;"></iframe> Another useful tool for exploring collocates in Voyant is _TermsBerry_, which can be found in the middle panel (top row) in the second tab. Although visually it's very different from _Links_ it also provides much of the same information. Whereas the default view in _Links_ shows data for the top 3 terms in the corpus (after the stoplist has been applied), _TermsBerry_ by default shows 75 of the top frequency words, so it's much denser with information. You can also click on the "Strategy" button at the bottom to determine how the initial seed words are shown: it can be "top terms" (by frequency) or "distinct terms" (higher frequency compared to other texts).


Whereas _Links_ shows lines between words that collocate, _TermsBerry_ indicates collocates as you hover over different terms. If you hover over any term the background colour of the other terms will update, with darker items showing more frequent collocates (the count is visible under each term). In what ways is this tool easier and harder to study collocates?

### Collocates

<iframe src="https://voyant-tools.org/tool/CorpusCollocates/?corpus=austen" style="width: 375px; height: 350px; float: right;"></iframe> The final tool that we'll mention is a more classic presentation of data in tabular format. By default it shows several high frequency terms (the keyword in the _Term_ column) as well as several collocate forms. One benefit of the tabular view is that results can be organized by sorting columns: terms, term counts, collocates, collocate counts. The search is another powerful aspect of this tools, allowing you to work with one or more keyword terms at a time, even word collocates of phrases (what terms occur close to "love him", for instance?). Again, what are the pros and cons of this tool compared to the others? Are they complementary?

## Collocates in Jupyter

![Jupyter](../images/jupyter48.png) For our exploration of collocates in Jupyter we'll follow a link into [Getting NLTK](https://nbviewer.jupyter.org/github/sgsinclair/alta/blob/master/ipynb/GettingNltk.ipynb) in the Art of Literary Text Mining with Jupyter.
