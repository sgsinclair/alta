# Format Conversion with Web Scraping with the Art of Literary Text Analysis

This is part of the [Art of Literary Text Mining](../) collection. This page is intended to briefly describe how to get started with format conversion, particularly with Juypter Notebooks.

### Plain Text

For better or for worse, the vast majority of text mining projects either start with plain text versions of the documents, or convert existing document to plain text. We identify three major kinds of conversion and pre-processing steps:

1. files are already in plain text but require some cleaning (to remove a license statement or regular page numbers, for instance)
1. files are in HTML or XML format in ways that are conducive to text extraction (we've already seen) and other pre-processing (especially thanks to libraries like BeautifulSoup)
1. files are in some other format that may require special or manual handling, especially for binary formats like MS Word and PDF.

For documents that are already in plain text, the easiest is often to make changes manually in the files or to use an application to make the same changes in multiple documents at a time (if the editor supports such functionality).

Let's work through a real example, three drafts screenplays for The Godfather movies, available from [IMSDb search](https://www.imsdb.com/search.php). If you type "Godfather" in the search you should get three hits:

#### Search results for 'godfather'

	Godfather (1971-03 Draft)
		Written by Mario Puzo,Francis Ford Coppola
	Godfather Part II (1973-09 Draft)
		Written by Mario Puzo,Francis Ford Coppola
	Godfather Part III, The (1979-03 First draft)
		Written by Mario Puzo,Francis Ford Coppola

Let's just work with two of the three scripts, the first two (the third has a slightly different format that confuses things somewhat, though it would be possible to use as well). Near the bottom of the first section and near the bottom of the page you'll find links to _Read "Godfather" script_, we can compile links for each document:

https://www.imsdb.com/scripts/Godfather.html
https://www.imsdb.com/scripts/Godfather-Part-II.html

Rather than save the HTML file to our hard drive, we will select the actual script and copy it into the clipboard (starting with **_THE GODFATHER_** and going until **THE END**: select that entire section and then copy it into the clipboard.

Now we need a plain text editor. Several very good ones exist, including [TextMate](https://macromates.com) for Mac and [Sublime](https://www.sublimetext.com) for multiple platforms, but we will use [Atom](https://atom.io), a relatively new kid on the block that has excellent GitHub integration. Start by downloading Atom, unzipping the download and placing the executable where you want it (I put in my Applications folder).

When Atom first opens you should open your LLCU-212 GitHub folder (any folder can be a project). Then from the _File_ menu select _Add Project Folder…_ and add a folder calld "Godfather" (without the quotes). Finally you can select _New File_ from the _File_ menu, paste the screenplay into the document, and then save the file in the "Godfather" folder with the name "Godfather.txt". Next get the [second screenplay](https://www.imsdb.com/scripts/Godfather-Part-II.html), select the actual text, copy to the clipboard, return to Atom, choose _New File_ from the _File_ menu, paste the contents, and save in the "Godfather" as "Godfather2.html".


## Voyant

![Voyant](../images/voyant48.png) 


## Jupyter Notebook

![Jupyter](../images/jupyter48.png) Our Juypyter notebook will walk through the following steps:
