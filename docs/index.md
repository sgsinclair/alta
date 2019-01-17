# The Art of Literary Text Mining

This is a meta-guide that is intended to help you work through our guides for _The Art of Literary Text Mining_.

## Guides

1. [The Art of Literary Text Mining for Voyant](./voyant/): Voyant is a *web-based* collection of text analysis and visualizations tools, it can be relatively easy to start using but is limited to the pre-packaged functionality that is already implemented.
1. [The Art of Literary Text Mining for Python Jupyter Notebooks](../ipynb/ArtOfLiteraryTextAnalysis.ipynb): Python is a programming language with a huge number of useful libraries but it can take a while to become proficient in any programming language. 
1. [The Art of Literary Text Mining for ObservableHQ and VoyantJS](https://beta.observablehq.com/@sgsinclair/alta): This uses Javascript as a core programming language (takes some effort to learn) but has the benefit of being highly shareable as web-based resources. This approach exposes some of the analytic and visualization functionality of Voyant while allowing for more customized processing.

Usually you would probably want to work through just one of these guides but there are cases when working with one or more guides together is preferable; this meta-guide is for this mixed approach.

Why work through the materials of more than one guide? One reason is to fully appreciate the strengths and weaknesses of more than one approach. We firmly believe that no one tool or even one framework is ideal for all problems and that it can be useful to be familiar with more than solution. Indeed, our three guides have their own pros and cons that can be significant for a given task or a given project. The following is a very simplistic view of some of the characteristics of each approach:

## Comparison

| | Voyant | Juypter | ObservableHQ+VoyantJS |
|-|-|-|-|
| **setup&nbsp;and&nbsp;configuration** | no setup for hosted version, easy desktop version | usually requires some setup | no setup | 
| **text&nbsp;analysis&nbsp;specificity** | text analysis specific | infinitely generalizable | mixed specificity of VoyantJS for text analysis and Javascript more generally |
| **shareable** | Voyant URLs of tools and corpora | compatible with GitHub | web-based |
| **scalable** | optimized for up to hundreds of documents | very scalable | somewhat limited to browser resources |

## Topics

* setup and configuration
* compiling a corpus
* pre-processing a corpus
* frequency
* distribution
* document similarity
* topic modelling
* sentiment analysis
* parts-of-speech
* named entity recognition
* semantic analysis

### Setup and Configuration

The first step with any tool or framework is to ensure that whatever setup and configuration needed are performed. Because of the nature of the technologies the work involved is different for each of our guides.

Voyant Tools is a hosted website [voyant-tools.org](https://voyant-tools.org) that requires no setup, no login, and no configuration. However, that simplicity comes with a price: the hosted version is widely used by people all over the world and that excerpts pressure on the server, which sometimes causes downtime and other issues. For this reason (and others, such as data privacy, it's highly recommended that you [download and install the Desktop version of Voyant Tools](https://github.com/sgsinclair/VoyantServer/wiki/VoyantServer-Desktop) – in most cases it's as simple as downloading a zip file, uncompressing it, and clicking on the application launcher.

Jupyter tends to be the most intensive solution to setup and configure, especially if you set it up on your local machine. There are a lot of instructions out there for getting setup, especially depending on platform on system preferences, but the [Getting Setup notebook](https://nbviewer.jupyter.org/github/sgsinclair/alta/blob/master/ipynb/GettingSetup.ipynb) is a good place to start.

ObservableHQ is also a hosted website [observablehq.com](https://observablehq.com). It's possible to visit ObservableHQ and make anonymous changes to a notebook (like this one), but in order to save changes you need to login through one of the authentication services (currently GitHub, Twitter and Google – because we can use GitHub to store data, we recommend that option).