# Getting Started with the Art of Literary Text Analysis

This is part of the [Art of Literary Text Mining](../) collection. This page is intended to briefly describe how to get setup and configured with our three environments: Voyant Tools, Juypter Notebooks, ObservableHQ.

So you want to do some text analysis, but where to start? Let's imagine that we have a favourite news source and we want to try to determine what's being discussed (without necessarily just reading the front page articles). You can do this with most websites and media outlets, but for the purposes of this example, let's say that we want to look at the Canadian Broadcasting Corporation (Canada's public Anglophone broadcaster) at https://cbc.ca

## Voyant

![Voyant](../images/voyant48.png) In Voyant analyzing the contents of a URL is dead simple, all that needs to be done is to visit the main page [voyant-tools.org](https://voyant-tools.org) and paste in the URL of interest. We can also use the query parameters (part of the URL) to specify an input argument:

	[https://voyant-tools.org/?<span style='background-color: yellow'>input=<span style='color: red'>https://cbc.ca</span></span>](https://voyant-tools.org/?corpus=9094634e2f37d5e29cf93431c4c7bb5a&input=https://www.cbc.ca)

The full interface can show some interesting aspects, but even just the summary points out some interesting aspects:

<iframe src="https://voyant-tools.org/?corpus=9094634e2f37d5e29cf93431c4c7bb5a&input=https://www.cbc.ca&view=reader" style="width: 50%; max-width: 500px; height: 300px"></iframe>