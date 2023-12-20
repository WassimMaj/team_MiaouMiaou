---
layout: page
title: Blue Click, Red Click 🖱️
subtitle: Decoding the matrix behind the political bias of Wikispeedia
cover-img: /assets/img/berlin.jpg
---
### Introduction {#top}

Today, Wikipedia is part of everybody’s life. It is the first source that most people will check when they want to get information. This website is maintained by volunteers through open collaboration, and what makes its strength, can also bring problems. Wikipedia aims to have a neutral point of view and stay strictly factual but can we guarantee this when anyone can become a contributor? A study [<sup>[1]</sup>](#ref) observed that a large number of Wikipedia editors change their behavior and focus on editing controversial topics when promoted to administrators, they might be biased (consciously or not) and influence these articles. This concern about bias in Wikipedia content leads us to consider how such biases might extend to user interactions with the platform, such as through the WikiSpeedia game. 

WikiSpeedia is a game where players are tasked with navigating from one Wikipedia article to another using only internal Wikipedia links. The key objective of this game is not just entertainment, but appeared to gather data on how humans perceive the semantic distance between different concepts. The paths that players take from the start article to the end article, along with the number of clicks and the time taken, offer valuable insights into the way people relate and categorize information.[<sup>[3]</sup>](#ref). We will use this insight to understand the effect of potential political bias. Our study aims to examine the political bias within Wikipedia and its potential impact on Wikispeedia players.


<mark> Introduire le dataset / ce qu'il a dedans  ??</mark>
<mark> Ouai je pense que c'est bien de dire qu'on a les paths de plusieurs joueurs et les articles associés</mark>

Our dataset is an extensive collection derived from the Wikispeedia game, featuring detailed records of how players moved from one Wikipedia article to another, a process we'll refer to as 'the path' in our subsequent analysis. This dataset encompasses 4,604 Wikipedia articles as they existed in 2009, meticulously documenting user navigation and thereby shedding light on patterns in the pursuit of information. It also captures the duration users spend on these paths, providing a window into their engagement levels and the complexity of the topics encountered. Furthermore, the dataset includes categorizations for each article, facilitating focused studies across a variety of knowledge areas. This rich, layered dataset serves as the foundation for our investigation into potential political biases in Wikipedia's content.

### What about Political bias and political figures in wikispeedia ?
Firstly, let’s define political bias : this refers to a tendency to orient or modify information to make a political position more attractive. To define that, plain text of the articles was assessed in relation to two other well-known sites that reproduce wikipedia in a politically biased way: [Rationalwiki](https://rationalwiki.org/wiki/Main_Page) and [Infogalactic](https://infogalactic.com/info/Main_Page). According to [Media Bias/Fact check](https://mediabiasfactcheck.com/), these websites are respectively recognized as having a <span style="color: lightcoral">left-wing</span>
 and <span style="color: lightblue">right-wing</span>
 bias. After training a machine learning model (BERT with SVM) on data scraped from these websites, Wikispeedia articles are classified according the bias they contain. The results are shown below: 

{% include repart_bias_2a1.html %}

We can see that most of articles in Wikispeedia are similar to Infogalactic and therefore classified as <span style="color: lightblue">right</span> wing.

But does this mean that articles in Wikispeedia are biased ? It is too early to say that, we need to go deeper inside our data.<mark> en soi selon notre model, la réponse c'est clairement oui ahaha </mark>
A good way to understand this bias is to look the repartition through each categories of articles to see if there is a notable difference.


<p align="center">
{% include repart_bias_categ_2a2.html %}
</p>


Even though most categories have a clear majority of articles with a <span style="color: lightblue">right</span> bias, in a few categories, such as chemistry or railway transport, they account for less than 50%. <mark>Jsais pas si y’a plus à dire</mark>
<mark>Oui toujours des trucs à dire</mark>
It seems that article categories can have a link with the political bias in the way they are written. It can be for many reasons but our hypothesis is that it come from the article' authors. Let's think about it. Wikipedia is collaborative website where anyone can write or complete articles. Who takes personal time to write an article on wikipedia ? Personnaly, I would not spend 4 hours of my time writting about a Ukrainian painter from the 18th century, but who would do it ? It has to be people passionated or at least very interested in the subject. In this case, a Ukrainian interested in painting from that time period would be more suceptible to write an article about it than me. <mark>exemple a peut etre modifier</mark>

This concept becomes particularly pertinent when we turn to politically charged topics like political parties, figures, or events. Here, the contributors are often those who hold strong opinions or affiliations, potentially coloring the articles with their biases.

To put this theory to the test, we specifically zoom in on political figures. They present a straightforward case for categorization based on political affiliations. Our method involved manually classifying political personalities based on their party or ideological leanings, using web sources for accuracy. We then correlated this classification with the perceived bias in their Wikipedia articles. The results of this analysis, revealing the intersection of political affiliation and content bias, are presented below.

{% include repart_bias_pol_2a3_1.html %}

{% include repart_bias_pol_2a3_2.html %}

<mark>Ptetre ajouter une P value ou autre analyse de correlation</mark>
 There is a trend of right-leaning bias across articles about political figures from various affiliations.
 Right 
<mark>J'attend le resultat pour finir le Paragraph</mark>


We now have a pretty good overview in the political biases in Wikispeedia articles. We now understand that there is some biases in the way articles are written and there might permeate the content we consume daily. This raises a crucial question: How do these biases translate into interactive online environments, specifically in games like Wikispeedia? In the next section, we delve into the Wikispeedia Analysis to investigate whether the potential biases in Wikipedia articles affect the way players navigate through this game.


### How does the bias affect players during their games ?

In order to answer this quesiton we found interesting to analyse some key metrics about the paths : 
- The percentage of back-clicks
- the mean rating
- the finished percentage 
- the mean time people take.

We correlate these metrics with the political bias of articles on the plot below :

<mark>Via Faut que tu marques 3-4 lignes sur comment ta fait ces analyses depuis les paths, j'ai pas capté comment tu prends les meantime par exemple vu que dans les paths t'as du droite et du gauche en meme temps <mark>

{% include repart_bias_araigne_3a.html %}

<mark>(about that, pourquoi on normalise aussi les percentage backlicks et finished/unfinished si c’est des % de base, donc de 0 à 1 ?) </mark>
<mark>Les valeurs sur le graphs quand o passe la souris devraient etre les moyennes <mark>
Well, this graph is iteresting. There are significant differences in the way 
It looks like blabla (développer sur le graph)

### Analysis of the players

We will now take a look at Wikispeedia’s player’s behaviors.
<mark> introduire/décrire plots 3bi et 3bii </mark>



{% include repart_pol_path_3b1.html %}

<p align="center">
<img src="assets/img/dolf.gif" alt=""/>
</p>

#### But is it Statistically significant ?
After performing a t-test on the political figures we can confirm that it is statistically significant as our p-value is close to 0 (1 x 10<sup>-62</sup>).

How does the bias of current article impact the next step in the path ?

{% include bias_n_3b3.html %}

If we at each step we picked a random article, we would get proportions that roughly match the overall distribution of the dataset (the solid line on the graph). We can clearly see a difference <mark> ** Do a statistical test ** </mark>. 
People tend to pick articles with a <span style="color: lightblue">right</span> bias or no bias more than expected, and less articles with a <span style="color: lightcoral">left</span> bias, no matter what article they come from. Do people tend to avoid articles with a <span style="color: lightcoral">left</span>-leaning bias ? 

We cannot say for sure ; other parameters can come into play. For example, do articles link to different kind of articles depending on their bias ? 
<mark> Faire un plot sur les biais des articles linké par rapport au biais de l'article sur lequel on est ? </mark>


### Conclusion
 




#### References {#ref}

[1] : Das, S., Lavoie, A., & Magdon-Ismail, M. (2016). Manipulation among the arbiters of collective intelligence: How Wikipedia administrators mold public opinion. ACM Transactions on the Web (TWEB), 10(4), 1-25.

[2] Hube, C. (2017, April). Bias in wikipedia. In Proceedings of the 26th International Conference on World Wide Web Companion (pp. 717-721).

[3] West, R., Pineau, J., & Precup, D. (2009, June). Wikispeedia: An online game for inferring semantic distances between concepts. In Twenty-First International Joint Conference on Artificial Intelligence.


[<sup>[top]</sup>](#top)