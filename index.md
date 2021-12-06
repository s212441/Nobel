{% include /images/bokeh.html %}
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

<div class="bk-root" id="591c7aa2-46e3-46c0-8095-335a88fb98b6" data-root-id="5927"></div>












