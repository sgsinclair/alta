# The Art of Literary Text Mining

This is a meta-guide that is intended to help you work through our guides for _The Art of Literary Text Mining_.

## Guides

![Voyant](images/voyant48.png) [The Art of Literary Text Mining for Voyant](./voyant/): Voyant is a *web-based* collection of text analysis and visualizations tools, it can be relatively easy to start using but is limited to the pre-packaged functionality that is already implemented.

![Jupyter](images/jupyter48.png) [The Art of Literary Text Mining for Python Jupyter Notebooks](../ipynb/ArtOfLiteraryTextAnalysis.ipynb): Python is a programming language with a huge number of useful libraries but it can take a while to become proficient in any programming language. 

![ObservableHQ](images/observable48.png) [The Art of Literary Text Mining for ObservableHQ and VoyantJS](https://beta.observablehq.com/@sgsinclair/alta): This uses Javascript as a core programming language (takes some effort to learn) but has the benefit of being highly shareable as web-based resources. This approach exposes some of the analytic and visualization functionality of Voyant while allowing for more customized processing.

Usually you would probably want to work through just one of these guides but there are cases when working with one or more guides together is preferable; this meta-guide is for this mixed approach.

Why work through the materials of more than one guide? One reason is to fully appreciate the strengths and weaknesses of more than one approach. We firmly believe that no one tool or even one framework is ideal for all problems and that it can be useful to be familiar with more than solution. Indeed, our three guides have their own pros and cons that can be significant for a given task or a given project. The following is a very simplistic view of some of the characteristics of each approach:

## Comparison

| | ![Voyant](images/voyant48.png)<br>Voyant | ![Jupyter](images/jupyter48.png)<br>Juypter | ![ObservableHQ](images/observable48.png)<br>ObservableHQ+VoyantJS |
|-|-|-|-|
| **setup&nbsp;and&nbsp;configuration** | no setup for hosted version, easy desktop version | usually requires some setup | no setup | 
| **text&nbsp;analysis&nbsp;specificity** | text analysis specific | infinitely generalizable | mixed specificity of VoyantJS for text analysis and Javascript more generally |
| **shareable** | Voyant URLs of tools and corpora | compatible with GitHub | web-based |
| **scalable** | optimized for up to hundreds of documents | very scalable | somewhat limited to browser resources |

## Topics

* [setup the environments](./setup/)
* [getting started](./startup/)
* [compiling a corpus](./compile/)
* pre-processing a corpus
* frequency
* distribution
* document similarity
* topic modelling
* sentiment analysis
* parts-of-speech
* named entity recognition
* semantic analysis
