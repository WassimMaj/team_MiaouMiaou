---
layout: page
title: Blue Click, Red Click 🖱️
subtitle: Decoding the matrix behind the political bias of Wikispeedia
cover-img: /assets/img/berlin.jpg
---
### Introduction {#top}

Today, Wikipedia is part of everybody’s life. It is the first source that most people will check when they want to get information. This website is maintained by volunteers through open collaboration, and what makes its strength, can also bring problems. Wikipedia aims to have a neutral point of view and stay strictly factual but can we guarantee this when anyone can become a contributor ? A study [<sup>[1]</sup>](#ref) observed that a large number of Wikipedia editors change their behavior and focus on editing controversial topics when promoted to administrators, they might be biased (consciously or not) and influence these articles. Our study aims to examine the political bias within Wikipedia and its potential impact on Wikispeedia players, a game where participants try to navigate to a specific article solely using hyperlinks within the current article. This game aims to characterize semantic distances between concepts [<sup>[3]</sup>](#ref). This will allow us to see if this semantic distance is influenced by bias.
  
  
<mark> Introduire le dataset / ce qu'il a dedans  ??</mark>

### What about Political bias and political figures in wikispeedia ?
Firstly, let’s define political bias : this refers to a tendency to orient or modify information to make a political position more attractive. To define that, plain text of the articles was assessed in relation to two other well-known sites that reproduce wikipedia in a politically biased way: [Rationalwiki](https://rationalwiki.org/wiki/Main_Page) and [Infogalactic](https://infogalactic.com/info/Main_Page). According to [Media Bias/Fact check](https://mediabiasfactcheck.com/), these websites are respectively recognized as having a <span style="color: lightcoral">left-wing</span>
 and <span style="color: lightblue">right-wing</span>
 bias. After training a machine learning model (BERT with SVM) on data scraped from these websites, Wikispeedia articles are classified according the bias they contain. The results are shown below: 

{% include repart_bias_2a1.html %}

We can see that most of articles in Wikispeedia are similar to Infogalactic and therefore classified as <span style="color: lightblue">right</span> wing.
Is this repartition equal through each categories of articles ? 

{% include repart_bias_categ_2a2.html %}

Even though most categories have a clear majority of articles with a <span style="color: lightblue">right</span> bias, in a few categories, such as chemistry or railway transport, they account for less than 50%. <mark>Jsais pas si y’a plus à dire</mark>
Let’s now take a look at the political people whose articles are in Wikispeedia. We determined theit political affiliation and the results are shown below. 

{% include repart_bias_pol_2a3_1.html %}

{% include repart_bias_pol_2a3_2.html %}


Having explored the political biases in Wikispeedia articles, we now understand that these biases might permeate the content we consume daily. This raises a crucial question: How do these biases translate into interactive online environments, specifically in games like Wikispeedia? In the next section, we delve into the Wikispeedia Analysis to investigate whether the potential biases in Wikipedia articles affect the way players navigate through this game.


### How does the bias affect players during their games ?

{% include repart_bias_araigne_3a.html %}

<mark>(about that, pourquoi on normalise aussi les percentage backlicks et finished/unfinished si c’est des % de base, donc de 0 à 1 ?) </mark>


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