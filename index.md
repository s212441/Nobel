## The network of Nobel Prize laureates 

This webpage showcases the work we did for the project assignment of the course Social graphs and interactions. 

### Introduction

We chose to build the network of Nobel Prize laureates, using a list of Nobel laureates found on [Wikipedia](https://en.wikipedia.org/wiki/List_of_Nobel_laureates#List_of_laureates), in which there is an edge between two laureates if one of the laureate's Wikipedia page contains a link to the other laureate's page. The network consists in 969 nodes and 3220 edges. We decide to add the attributes year, prize, age, country of birth and gender to the nodes of the network. 

Through our analysis of the network, we would like to better understand Nobel Prize laureates and the prizes themselves. In particular, we would like to know what characterizes Nobel laureates in terms of age, gender and nationality, how they are connected to each other and what are the communities of laureates. Finally, we will analyze the Nobel lectures of the laureates, that we extracted from nobelprize.org, to understand their sentiments and how they evolve through time. 

### Network visualization

Below, we visualize the network, where laureates are represented by nodes whose size is proportional to their degree and which are colored according their prize, and edges are colored in red if they connect laureates that were awarded different prizes. 

![Network visualization](/images/Network.png)

Prizes seem to form clusters. But whereas Economics, Peace and Literature form three distinguishable clusters, the scientific prizes, Physics, Chemistry and Physiology or Medicine, seem to form one big cluster. Indeed, these three scientific fields are interdependent, so their clusters are highly interconnected. In addition, the Economics, Peace and Literature clusters seem quite interconnected and well separated from the science cluster, with Peace lying between Literature and Economics which is a little farther. Nevertheless, there is still a significant amount of links that connect these three prizes to the science cluster, revealing the interdependency of the fields. 

Moreover, four bigger nodes stand out: the biggest node of the network, which is Albert Einstein in Physics, followed by the European Union in Peace, and two black nodes, Linus Pauling and Marie Curie, in the science cluster.

You can explore yourself the network with the interactive visualization below and look at the different laureates and their attributes. 

<iframe src="/images/bokeh.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>







# SENTIMENT

Something very interesting that can be combined with a network analysis, is the sentiment analysis of the nodes. We of course did that in our project too. In order to extract sentiment for the Nobel Laureates (nodes), we need a text that is related with them, that contains some sentiment. As the WikiPages that we used previously, are sentiment-neutrally created, we could not use them for sentiment analysis. 

<div style="text-align: center;" markdown="1"> But what kind of text could possibly contain some sentiment for the Laureates? </div>

<img src="\images\Question-Mark.png" alt="drawing" width="100"/>

Yes you guessed correctly! The answer is their Nobel Prize Lectures. The Nobel Lectures, are the Lectures the Laureates give before or after receiving their prize. It is a text, that all (or most) Laureates have created, and also contain some sentiment. So this seems like a very good source of sentiment for our project.

The Nobel Lectures though do not exist in an opensource library that we can just download. So we had to create a webcrawler, using the *selenium* library in python and crawl through the different pages of the official website for Nobel Prizes (nobelprize.org). This website, contains the information we need in most cases, but the format between different webpages differ a lot, so we found much information but not for all the Laureates.

As now we have a dataset, that we can extract sentiment, we now need to find a tool to do that. Thankfully, there is a very good and sophisticated library called VADER for this job. Th VADER lexicon calculates the sentiment of whole sentences and contains evaluations for symbols and emojis, so its results are better than other methods in many cases. The scores created by the VADER methods, lie in the interval [-1,1], with -1 indicating very negative sentiment, 1 indicating very positive sentiment, while 0 accounts for neutral sentiment.

Now, let's see some results!

First of all let's see the histogram of the sentiment between Nobel Prize Laureates.

<img src="/images/sent_hist.png" alt="drawing" width="800"/>

As we can see from the figure above the sentiments of the Laureates are concentrated around the value $0.1$. This means that the texts of their Nobel lectures are not much emotional, but are at least positive in most cases.

We can also find  who have the most positively, or negatively emotional Lectures among the laureates. The results for this experiment are depicted in the figures below.

<img src="/images/happiest_lau.png" alt="drawing" width="500"/> <img src="/images/saddest_lau.png" alt="drawing" width="500"/>

As we can see, the most negative emotiolanlly Lectures, were given by organizations that received the Peace award, and not individuals. This pattern is very interesting, and we wonder why is that happening. The answer may be that these Organizations fight against something negative happening in the globe, and this is what they talk about in their lecture. 
Something that also needs to be commented is themost positive Laureate *John B. Goodenough*, even though he is a chemist, and his lecture was mostly about figures and mathematical formulas, he holds the most positive score. This is because he refers to technologies that are going to have very positive results to the world.
Also, the most negative sentimented Laureate, is a *Élie Ducommun*, even though he won the nobel Peace Prize, in his Lecture, he is talking about "The Futility of War Demonstrated by History", and that is the reason of the very negative score. 

Last but not least we created the bar plot of the average sentiment per year for the different categories. The category that is mostly interesting totalk about is the sentiment of Laureates awarded the Literature Nobel Prize. In the figure below we can see why.

<img src="/images/literature_years_sen.png" alt="drawing" width="600"/>

As we observe above, the sentiment in Literature Lectures between 1901 and 2020, changes between periods.

