---
layout: home
title: War impact on cinema
subtitle: Looking at wars trough the lens of cinema
---

<style>body {text-align: justify}</style>

Wars impact not only the people who experience them, but also the culture as a whole. Using film metadata sets extracted from Wikipedia and Freebase, we explore the impact of war on film. **What is the impact of war on film production? How does each country show the war? Or doesn't show it?**

![]({{ 'assets/img/vietnamcamera.jpg' | relative_url }})

During wartime, it is common for filmmakers to produce war-themed films that explore the experiences of soldiers, civilians, and others directly affected by the conflict. These films may focus on the heroism and sacrifice of soldiers, the atrocities and suffering of war, or the psychological effects of combat on individuals and families.

After wars are over, filmmakers may continue to produce war-themed films that explore the long-term effects of conflict on society, or that revisit the events of war from a historical perspective. These films may take a more critical view of the war, examining its causes, consequences and legacy.

### War films in cinema...

War films never had such a large share of film production as during World War II.\\
**From 1939 to 1945 roughly 10 % of films were War Films.**\\
Let's have a look on the proportion of war films over the years:\\
![Not found]({{ 'assets/img/WarFilmsByYear.png' | relative_url }})

To better illustrate the impact of war, we zoom on two wars: the World War II and the Vietnam War.






Case Study : WW2
----------------

#### WW2 recap
[World War II](https://en.wikipedia.org/wiki/World_War_II) lasted from 1939 to 1945. It involved the vast majority of the world's nations - including all the major powers - who ended up forming two opposing military alliances: the Allies and the Axis. It was the largest war in history, directly involving over 100 million people in more than 30 countries. In a state of "total war", the main participants put all their economic, industrial and scientific capacities at the service of the war effort, erasing the distinction between civilian and military resources. Marked by massive civilian deaths, including the Holocaust, and the strategic bombing of industrial and population centers, it resulted in between 50 and 70 million deaths.

![Not found]({{ 'assets/img/debarquement.jpg' | relative_url }})



## Lets do topic analysis
-------------------------
#### Communities detection for WWII

We wanted to find out what types of movies the different countries made in the second world war and if they were different from the movies they made before or after. The first thing we noticed was the number of movies: if we look at the number of movies produced in each belligerent country we notice that the only countries that increased their movie production during the war are the USA and Italy. And we see that after the war the film production of France, Japan and Italy increased drastically: 3 fold for France and Japan and 6 fold for Italy. The movie production for the US, USSR and UK post war are slightly below their production prewar. The movie industry of Germany became very small after the war.

We can see here different behaviors for each country. A war takes a lot of resources and industries that are considered as non essential often see their production strictly decline. The fact that a country’s film production doesn’t decrease and even increases for Italy and the US reveals that these countries invested in their movie industry and believed it was essential. Indeed, they can be fairly important for morale. Nonetheless, they are considered as less important than tanks and weapons for all the other countries as their film production decreases.

This analysis is very surface level and depends on the movies in the dataset, we therefore need to take these observations with a grain of salt. To have more generalizable results that do n’t depend on the number of movies, but on the subjects in the movies we decided to do some topic analysis using LDA (Latent Dirichlet Allocation) for each country before, during and after the war. This didn’t produce any relevant information as a wide variety of movies are produced in each country and any underlying topic is hard to isolate with this method. We therefore decided to do LDA on clusters of movies based on their similarity. To cluster the movies, we linked each movie to every other movie whose plot summary was similar (using spaCy’s similarity metric). We then used the Louvain method to find clusters. Finally using LDA we could analyze each cluster and found this for all the USSR’s movies before the war:

![Not found]({{ 'assets/img/main.jpg' | relative_url }})

And for American movies during the war we found that each cluster was very unique and different:


- | - | -
![Not found]({{ 'assets/img/soldier.jpg' | relative_url }}) | ![Not found]({{ 'assets/img/heart.jpg' | relative_url }}) | ![Not found]({{ 'assets/img/mickey.jpg' | relative_url }})


We found that each cluster had a clear title, here the first one is about cartoons with words like: “Tom”, “Jerry”, ”Donald”, ”Daffy” and “Elmer”.\\
The second one is clearly about love and family with words like: “find”, “Love”, ”marriage”, “husband”, ”marry”, ”family” and ”meet”.\\ 
The third one is clearly about war with words like: “kill”, ”German”, ”nazi”, ”Japanese”, ”death”, ”men” and ”captain”.

We then did this analysis of topics for every cluster, for every country, before, during and after the war and got this: 

|   Country  |  01.09.1929- 01.09.1939 | 01.09.1939- 02.09.1945 | 02.09.1945- 02.09.1955|
|:-:	|:-:	|:-:	|:-:	|
|   USA   |   (Investigation,crime)<br>(love)<br>(unclear)   |   (cartoons)<br>(war)<br>(love, family) |  (love)<br>(cartoons)<br>(fugitives,escape) |
|   GERMANY   |   (Hitler,nationalism,nazi)<br>(investigation)  |   (prussian war)<br>(Aristocracy) |  (WWII)<br>(unclear) |
|   FRANCE   |   (WWI)<br>(crime)<br>(unclear)   |   (Marriage, love)<br>(Marriage, love) |  (WWII)<br>(unclear) |
|   ITALY   |   (love,war)<br>(unclear)   |   (soldiers,religion)<br>(Family,struggle) |   (WWII)<br>(political conflict)<br>(love)(unclear) |
|   UK   |   (fugitives, escaping, war)<br>(love,money)<br>(unclear)<br>(unclear)   |   (Nazis, war)<br>(Aviation)<br>(Dramas)<br>(unclear)<br>(unclear) |   (WWII)<br>(love)<br>(unclear) |
|   USSR   |   (war,revolution)<br>(workers)<br>(WWI, Germany)<br>(workers,communism)   |   (war) |   (WWII)<br>(unclear) |
|   JAPAN   |   (tradition, family)<br>(unclear)   |   (tradition, history)<br>(industry, social status) |   (science fiction)<br>(relationships)<br>(unclear) |

[1] Each cluster is in parenthesis\\
[2] Clusters that have too many different movies, where LDA cannot extract the topics are defined by (unclear)

Here it is interesting to note that during the war most countries, besides the UK, don’t have any unclear clusters, which is not the case for clusters before and after the war. This might be the consequence of government oversight, people cannot make any type of movie that they want, they have to fit a political agenda which wants to say certain things. For Germany it is to glorify themselves and their leaders by talking about the war that they won and the upper class. 

For Japan they talk about their traditions and social status, to remind their people that they are fighting to protect their traditions and that they are honor bound to do so.

In America they have two types of movies: the ones to distract and entertain the population with cartoons and love movies and movies talking directly about the war. Where love movies can also be considered as movies to remind people of the American way of life and cartoons can be used for propaganda: 

<div style="text-align: center;">
{% include youtube_embed.html id="qy_MQkaJ5WE" %}
</div>

-------

<div style="text-align: center;">
{% include lda.html max-width="200px" %}
</div>

War, death, family and love...
------------------------------
#### Axis countries 

##### Germany
**War, death and family are recurring topics in films produced in post-war Germany**.\\
During the war and the pre-war period it was mostly the family that was a recurent topic.\\
Love does not seem to be a recuring topic in german films.\\
![Not found]({{ 'assets/img/topicgermany.jpg' | relative_url }})

##### Italy
**Unsurprisingly, the family is an important topic in Italy until the fall of fascism.**\\
The peaks in love and death topics in the pre-war period are most likely over representation due to the small number of films.\\
Death is a more reccurent topic in italian films during the war than it was in german films.\\
On the other hand, war is a less recurrent topic in post-war italian films than it was for post-war german films.\\
![Not found]({{ 'assets/img/topicitaly.jpg' | relative_url }})

##### Japan
**The topic of family is an important topic even after the war in japanese films.**\\
As with german films, love is not a recurring topic in japanese films.\\
![Not found]({{ 'assets/img/topicjapan.jpg' | relative_url }})


#### Allies countries

##### France
**Among all 6 countries, France is the country where the topic of love is the most recurrent.**\\
Family is also a recurring topic in french films.\\
War is way less talked about in french films during the war than death.\\
![Not found]({{ 'assets/img/topicfrance.jpg' | relative_url }})

##### United Kingdom
**Family and death are recuring topics in the english films.**\\
The war topic gains in popularity during the war for the english films.\\
![Not found]({{ 'assets/img/topicuk.jpg' | relative_url }})

##### United States of America
The topics are mostly similar to the English topics.\\
![Not found]({{ 'assets/img/topicusa.jpg' | relative_url }})




Lets do sentiment analysis...
-----------------------------
##### On the 1930-1955 period (we include the pre-war and post-war period)
#### Axis countries : 
For **Germany** produced films, we can observe that overall sentiment is **negative in the post-war period** (1946-1951). We can note that in 1939, has a a overall strong positive sentiment. Perhaps this is due to a large proportion of _propaganda_ films.\\
For **Italy** produced films, we find a post-war period that has overall **negative** compound sentiment, (1945-1951) as in Germany. \\
For **Japan** produced films, the pre-war period was positive (until 1936) and since then, it seems to be mostly negative.\\
![Not found]({{ 'assets/img/winlose1.png' | relative_url }})


#### Allies countries :
For **France** produced films, the year of _liberation_ has a _positive_ overall sentiment.\\
For **United Kingdom** and **United States of America** produced films, the amount of produced films is much bigger and thus the sentiment analysis is _less fruitful_. But we can still note that the **sentiment of English films in 1944 and 1945 is more positive than American ones**. It could hint in a different reception of victory for the two countries.\\
Also interesting is the fact that the general sentiment of films is a bit more _negative_ after the country enters the war (1939 for UK and 1941 for USA).\\
![Not found]({{ 'assets/img/winlose2.png' | relative_url }})







Case Study : Vietnam War
------------------------

#### Vietnam War recap

The [Vietnam War](https://en.wikipedia.org/wiki/Vietnam_War) started in 1955 and ended in 1975. It involved many countries, but was mainly a conflict between the USSR and China and the USA on Vietnamese soil. In popular culture, it is known for a rise of anti-war sentiment with the "Make love, not war" movement. How can we see these characteristics reflected in the movies made around that time ? Did the movie industry reflect these sentiments ?

![Not found]({{ 'assets/img/flower.jpeg' | relative_url }})

First, let's look at the percentage of war movies made throughout the years around the Vietnam War, in the world and in the USA.

![Not found]({{ 'assets/img/vietnam1.jpg' | relative_url }})

We can immediately see that the USSR has an enormous proportion of war films, getting close to 40% in 1970 and 1971. It is important to note that we have much less data for movies from the USSR in that time : 341 films, compared to 8510 American films. The median number of films made by year in the USSR during the given time period is 9. However, it is still interesting to see that the Soviet Union made a large proportion of war films per year.  
Since our dataset holds mostly American movies, it makes sense that the graphs for war films in the world and war films in the USA follow roughly the same shape. However, it does seem like there is a larger proportion of war films made in the USA during that time compared to the rest of the world, hitting more than 10% of all films in 1958, 1963 and 1965. After the end of the war, the proportion of war films in the USA drops quickly to the global average. 

Now let us look at the proportion of anti-war films. We note that there are no anti-war films made in the Soviet Union in our dataset ; **this can be due to censorship being very strict in the USSR, or it can simply be due to the lack of data.**

![Not found]({{ 'assets/img/vietnam2.jpg' | relative_url }})

As we can see, anti-war films are a lot less common in the rest of the world than they are in the USA. We can also see that anti-war films are concentrated around the time of the Vietnam War. To see whether this is statistically significant, we ran t-tests comparing the proportion of anti-war films in the USA during the Vietnam war and before and after. We found a p-value of 0.0001 < 0.05, so we can conclude that it is statistically significant. On the other hand, in the rest of the world, the p-value for the comparison of anti-war movies in these time periods is 0.27 >> 0.05, so it is not statistically significant.

This allows us to conclude that in the USA particularly, **anti-war movies are a movie genre that can be linked to the time period of the Vietnam war**. This is interesting given that it is far from the only war the USA has been belligerent in, and they have also participated in many wars since.

We now perform topic analysis on American anti-war films that were released around the time of the Vietnam War.

|Topic           |Normalized frequency |
|:---------------|:--------------------|
|military        |0.015220979277461948 |
|war             |0.013570511644966074 |
|weapon          |0.012836970474967908 |
|fight           |0.009352649917476618 |
|kill            |0.00715202640748212  |
|leader          |0.00715202640748212  |
|negative_emotion|0.00715202640748212  |
|crime           |0.0060517146524848705|
|death           |0.005684944067485788 |
|prison          |0.005501558774986246 |

The above are the ten most prevalent topics in anti-war films in America during the Vietnam War. From this, we can see that these movies generally used the angle of showing how terrible and brutal wars are, as opposed to, for example, showing a utopian peace time as a form of critique of war.

We now perform the same topic analysis on war films.

|Topic           |Normalized frequency |
|:---------------|:--------------------|
|military        |0.012595477421389684 |
|war             |0.012348641717976496 |
|fight           |0.009976276346283066 |
|leader          |0.007905599056539089 |
|weapon          |0.007357075271176446 |
|negative_emotion|0.006979965168739629 |
|kill            |0.005697790820454452 |
|family          |0.005601799158015989 |
|children        |0.005306967623383569 |
|death           |0.005121840845823677 |

These are practically the same topics, however, they do also include "family" and "children" as topics.

### The words "Vietnam" and "War" in American movies
Do these movies only talk about the country of Vietnam in relation to the war ? To explore this, we first look at the proportion of American movie summaries that contain the word "Vietnam" over time. We do not repeat this analysis for the USSR, since there are only 2 movies made there that include the word "Vietnam" in their summary.

![Not found]({{ 'assets/img/vietnam3.jpg' | relative_url }})

As we can see, American movies did not discuss Vietnam at all before the war. We can also see that the difference between the proportion of these movies made during and after the war is not statistically significant, similarly to Germany and World War II. However, visually, we can see that the proportion of movies mentioning Vietnam goes down a lot after the end of the war.

We now do topic analysis on the American movies that include the word "Vietnam'' in the summary.

|Topic           |Normalized frequency |
|:---------------|:--------------------|
|negative_emotion|0.0075360372587396605|
|war             |0.007486035115790677 |
|family          |0.006978870523022415 |
|fight           |0.006821720930897038 |
|children        |0.006578853379430547 |
|crime           |0.00642170378730517  |
|military        |0.006414560624026744 |
|death           |0.00577881909224681  | 
|home            |0.00536451562209809  |
|traveling       |0.005350229295541237 |

From these topics, we can see that war and violence are major topics in American movies that somehow include Vietnam. Finally, we count the percentage of American movies that include the words "vietnam" and "war".
We can see that 77% of movies that include the word "Vietnam" in the summary also include the word "war" in the summary. This, along with the above topic analysis, shows us that American movies that somehow discuss Vietnam usually also discuss war, and probably discusses the Vietnam War. Similarly, of all American movies that include the word "Germany", 84% also include the word "war" or the word "nazi".







Take home message
-----------------

War has had a significant impact on film, both in terms of the themes and genres of films produced, as well as the general feeling and perspective on war that is portrayed in these films.
  
