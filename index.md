---
layout: home
title: War impact on cinema
subtitle: Looking at wars through the lens of cinema
---

<style>body {text-align: justify}</style>

Wars impact not only the people who experience them, but also the culture as a whole. Using film metadata sets extracted from Wikipedia and Freebase, we explore the impact of war on film. **What is the impact of war on film production? How does each country show the war? Or doesn't show it?**

![]({{ 'assets/img/vietnamcamera.jpg' | relative_url }})

##### War films in cinema…

During wartime, it is common for filmmakers to produce war-themed films that explore the experiences of soldiers, civilians, and others directly affected by the conflict. These films may focus on the heroism and sacrifice of soldiers, the atrocities and suffering of war, or the psychological effects of combat on individuals and families.

After wars are over, filmmakers may continue to produce war-themed films that explore the long-term effects of conflict on society, or that revisit the events of war from a historical perspective. These films may have a more critical perspective on the war, examining its causes, consequences and legacy.

**Let's have a look on the proportion of war films over the years:**

![Not found]({{ 'assets/img/WarFilmsByYear.png' | relative_url }})

War films never had such a large share of film production as during World War II.\\
**From 1939 to 1945 roughly 10 % of films were War Films.**

To better understand what happened, we will make an in-depth analysis on the Second World War and its impact on cinema :




Case Study : WW2
----------------

**Recap :** [World War II](https://en.wikipedia.org/wiki/World_War_II) lasted from 1 September 1939 to 2 September 1945. The main participants were the USA, the UK, France, Germany, Japan, Italy and the URSS. Note that the USA joined the war only in 1941. It was the largest war in history, and therefore had a strong and lasting impact on culture, including the movie industry.


![Not found]({{ 'assets/img/debarquement.jpg' | relative_url }})

Let's do sentiment analysis...
-----------------------------
##### On the 1930-1955 period (we include the pre-war and post-war period)
#### Axis countries :
For **German** produced films, we can observe that the overall sentiment is **negative in the post-war period** (1946-1951). We can note that in 1939, it had an overall strong positive sentiment. Perhaps this is due to a large proportion of _propaganda_ films.\\
For **Italian** produced films, we find a post-war period that has overall **negative** compound sentiment, (1945-1951) as in Germany. \\
For **Japanese** produced films, the pre-war period was positive (until 1936) and since then, it seems to be mostly negative.\\
![Not found]({{ 'assets/img/winlose1.png' | relative_url }})


#### Allied countries :
For **France** produced films, the year of _liberation_ has a _positive_ overall sentiment.\\
For **United Kingdom** and **United States of America** produced films, the amount of produced films is much bigger and thus the sentiment analysis is _less fruitful_. But we can still note that the **sentiment of English films in 1944 and 1945 is more positive than American ones**. It could hint at a different reception of victory for the two countries.\\
Also interesting is the fact that the general sentiment of films is a bit more _negative_ after the respective countries enter the war (1939 for UK and 1941 for USA).\\
![Not found]({{ 'assets/img/winlose2.png' | relative_url }})




## Let's do topic analysis

War, death, family and love...
-----------

#### Axis countries

##### Germany
![Not found]({{ 'assets/img/topicgermany.jpg' | relative_url }})
**War, death and family are recurring topics in films produced in post-war Germany**.\\
During the war and the pre-war period it was mostly family that was a recurrent topic.\\
Love does not seem to be a recurring topic in German films.


##### Italy
![Not found]({{ 'assets/img/topicitaly.jpg' | relative_url }})
**Unsurprisingly, family was an important topic in Italy until the fall of fascism.**\\
The peaks in love and death topics in the pre-war period are most likely over representation due to the small number of films.\\
Death is a more recurrent topic in Italian films during the war than it was in German films.\\
On the other hand, war is a less recurrent topic in post-war Italian films than it was for post-war german films.


##### Japan
![Not found]({{ 'assets/img/topicjapan.jpg' | relative_url }})
**The topic of family is an important topic even after the war in Japanese films.**\\
As with German films, love is not a recurring topic in Japanese films.



#### Allied countries

##### France

![Not found]({{ 'assets/img/topicfrance.jpg' | relative_url }})

What is interesting is that in 1940, there was a shift of topics in French films: family and love movies were at an all time high and the number of war movies dropped. This is a clear consequence of the defeat of France in 1940 : the films were probably under censorship of the new government, which preferred love and family movies over war movies.
**Among all 6 countries, France is the country where the topic of love is the most recurrent.**

##### United Kingdom

![Not found]({{ 'assets/img/topicuk.jpg' | relative_url }})
**Family and death are recurring topics in English films.**\\
The war topic gains in popularity during the war for the english films.

##### United States of America
![Not found]({{ 'assets/img/topicusa.jpg' | relative_url }})

It is interesting to note that the topics remain relatively constant, except for 1943 which sees a little increase in war films. This makes sense as the USA joined the war in 1941 and a movie takes some time to produce.


#### Communities detection for WWII

We wanted to find out what types of movies the different countries produced during WW2 and if they were different from the movies they produced before or after. 

The first thing we noticed was the number of movies:

![Not found]({{ 'assets/img/8graphs.jpg' | relative_url }})

If we look at the number of movies produced in each belligerent country, we notice that most countries produced less movies during the war, with the movie production declining and reaching a low point in 1945. But for some countries like Italy, Germany, or the USA their movie production actually goes up a bit at the start of the war, with 1942 being the year with the most movies produced for the USA in this time period. We can also notice that after the war Italy, Japan and France really increased their film production, maybe suggesting an economic or cultural boom
.
We can see here different behaviors for each country. A war takes a lot of resources, and industries that are considered non-essential often see their production strictly decline. The fact that a country’s film production doesn’t decrease and even increases for Italy and the USA reveals that these countries invested in their movie industry and considered it essential. Indeed, they can be fairly important for morale. Nonetheless, they are still considered as less important than tanks and weapons for all the other countries, as their film production decreases.

This analysis is very surface level and is very sensitive to the bias of the dataset, so we must take these observations with a grain of salt. To have more generalized results that don’t depend on the number of movies, but on the subjects in the movies, we decided to do some topic analysis using the LDA method (Latent Dirichlet Allocation) for each country before, during and after the war. 
% include lda_american.html%}
This is hard to analyze as the LDA method often has trouble creating coherent clusters and you have to set how many clusters are present in each country’s film production. . We therefore decided to use the LDA method on clusters of movies based on their similarity. To cluster the movies, we linked each movie to every other movie whose plot summary was similar (using the spaCy’s similarity metric). We then used the Louvain method to find clusters. Finally, using the LDA method, we could analyze each cluster and found this for clusters of American movies during the war:

![Not found]({{ 'assets/img/mickey.jpg' | relative_url }})

![Not found]({{ 'assets/img/heart.jpg' | relative_url }})

![Not found]({{ 'assets/img/soldier.jpg' | relative_url }})

We found that each cluster had a clear topic, here the first one is about **cartoons** because the most frequent words in the cluster are: “Tom”, “Jerry”, ”Donald”, ”Daffy” and “Elmer”.\\
The second one is clearly about **love and family** with words like: “find”, “Love”, ”marriage”, “husband”, ”marry”, ”family” and ”meet”.\\
The third one is clearly about **war** with words like: “kill”, ”German”, ”nazi”, ”Japanese”, ”death”, ”men” and ”captain”.

We then did this analysis of topics for every cluster, for every country, before, during and after the war and got the following clusters:

|   Country  |  01.09.1929- 01.09.1939 | 01.09.1939- 02.09.1945 | 02.09.1945- 02.09.1955|
|:-:    |:-:    |:-:    |:-:    |
|   USA   |   (Investigation,crime)<br>(love)<br>(<span style="color:blue">unclear</span>)   |   (cartoons)<br>(war)<br>(love, family) |  (love)<br>(cartoons)<br>(fugitives,escape) |
|   GERMANY  |   (<span style="color:red">Hitler,nationalism,Nazis</span>)<br>(investigation)  |   (prussian war)<br>(Aristocracy) |  (<span style="color:red">WWII</span>)<br>(<span style="color:blue">unclear</span>) |
|   FRANCE	|   (WWI)<br>(crime)<br>(unclear)   |   (Marriage, love)<br>(Marriage, love) |  (<span style="color:red">WWII</span>)<br>(<span style="color:blue">unclear</span>) |
|   ITALY   |   (love,war)<br>(<span style="color:blue">unclear</span>)   |   (soldiers,religion)<br>(Family,struggle) |   (<span style="color:red">WWII</span>)<br>(political conflict)<br>(love)(<span style="color:blue">unclear</span>) |
|   UK   |   (fugitives, escaping, war)<br>(love,money)<br>(<span style="color:blue">unclear</span>)<br>(<span style="color:blue">unclear</span>)   |   (<span style="color:red">Nazis,War</span>)<br>(Aviation)<br>(Dramas)<br>(<span style="color:blue">unclear</span>)<br>(<span style="color:blue">unclear</span>) |   (<span style="color:red">WWII</span>)<br>(love)<br>(<span style="color:blue">unclear</span>) |
|   USSR  |   (war,revolution)<br>(workers)<br>(WWI, Germany)<br>(workers,communism)   |   (war) |   (<span style="color:red">WWII</span>)<br>(<span style="color:blue">unclear</span>) |
|	JAPAN   |   (tradition, family)<br>(<span style="color:blue">unclear</span>)   |   (tradition, history)<br>(industry, social status) |   (science fiction)<br>(relationships)<br>(<span style="color:blue">unclear</span>) |

\* Each cluster is in parenthesis\\
\*\* Clusters that have too many different movies, where the LDA method cannot extract the topics are defined by (<span style="color:blue">unclear</span>)

First, **<span style="color:blue">unclear</span> clusters are a consequence of variety in movie production**. When the movies are too different, the LDA method has trouble extracting the different topics. And here we note that during the war, most countries besides the UK didn't have any <span style="color:blue">unclear</span> clusters. This is not the case for clusters before and after the war. **This might be the consequence of government oversight:in times of war, people cannot make any type of movie that they want, they have to fit a political agenda which wants to say certain things. 

For Germany, it is to glorify themselves and their leaders by talking about the wars that they had won previously and by talking about the upper class.**\

In Japan, their films talk about their traditions and social status, to remind their people that they are fighting to protect their traditions and that they are honor-bound to do so.

In America, there are two types of movies: the ones to distract and entertain the population with cartoons and romantic movies and the ones talking directly about the war.Both romantic movies and cartoons can be considered as propaganda for the American way of life.:

<div style="text-align: center;">
{% include youtube_embed.html id="qy_MQkaJ5WE" %}
</div>

In France, there is no war cluster, only love and family. This highlights the political situation of France at the time, which was under occupation. There was probably some censorship done by the German government and the filmmakers couldn’t talk about their situation or the war.

10 years after the war, we can say that a larger variety of films come out, as the LDA method has more trouble extracting topics. Except for the topic of WWII, which is present in all European countries. This makes sense as the citizens that suffered the war are mostly European. American citizens didn’t see what happened in the continent and therefore didn’t feel the same need to represent it. Whilst the Japanese didn’t suffer the war in the same way, their traumatic experience was the atomic bomb, which they represented via science fiction and Godzilla. 
> “The earlier Godzilla films, especially the original, portrayed Godzilla as a frightening nuclear-spawned monster. Godzilla represented the fears that many Japanese held about the atomic bombings of Hiroshima and Nagasaki and the possibility of recurrence.”
Wikipedia page for [Godzilla](https://en.wikipedia.org/wiki/Godzilla)



After this in depth look into World War Two, we realized that this was a war which was mostly favorably depicted in movies during the war as it was used as a tool for propaganda. We therefore wondered how movies were affected by the Vietnam war, as it is known for a rise of anti-war sentiment with the "Make love, not war" movement. We wondered whether we would be able to recognize these characteristics in the movies made around that time. Did the movie industry reflect these sentiments ?







Case Study : Vietnam War
------------------------


**Recap :** The [Vietnam War](https://en.wikipedia.org/wiki/Vietnam_War) started on November 1, 1955 and ended on April 30, 1975 It involved many countries, but was mainly a conflict between the USSR, China and the USA on Vietnamese soil. 

![Not found]({{ 'assets/img/flower.jpeg' | relative_url }})

In the dataset, there are only very few Vietnamese movies made before the 2000s, and only 28 overall. Since this is so little compared to movies in the USSR and in the USA, we decided that we do not have enough data to be able to compare them with Vietnamese movies. We therefore do not consider Vietnamese movies in this analysis.

First, let's look at the percentage of war movies made throughout the years around the Vietnam War, in the world and in the USA.

![Not found]({{ 'assets/img/vietnam1.jpg' | relative_url }})

We can immediately see that **the USSR has an enormous proportion of war films, getting close to 40% in 1970 and 1971**. It is important to note that we have much less data for movies from the USSR in that time : 341 films, compared to 8510 American films. The median number of films made by year in the USSR during the given time period is 9. However, it is still interesting to see that the Soviet Union made a large proportion of war films per year.  
Since our dataset holds mostly American movies, it makes sense that the graphs for war films in the world and war films in the USA follow roughly the same shape. However, it does seem like there is a larger proportion of war films made in the USA during that time compared to the rest of the world, hitting more than 10% of all films in 1958, 1963 and 1965. After the end of the war, the proportion of war films in the USA dropped quickly to the global average.

Now let us look at the proportion of anti-war films. We note that there is only one anti-war film made in the Soviet Union in our dataset, and it’s from 1996, which is after the timespan we are considering here. **This can be due to censorship being very strict in the USSR, or it can simply be due to the lack of data.**

![Not found]({{ 'assets/img/vietnam2.jpg' | relative_url }})

As we can see, anti-war films are a lot less common in the rest of the world than they are in the USA. We can also see that anti-war films are concentrated around the time of the Vietnam War. To see whether this is statistically significant, we ran t-tests comparing the proportion of anti-war films in the USA during the Vietnam war and before and after. We found a p-value of 0.00003 < 0.05, so we can conclude that it is statistically significant. On the other hand, in the rest of the world, the p-value for the comparison of anti-war movies in these time periods is 0.27 >> 0.05, so it is not statistically significant.

This allows us to conclude that in the USA particularly, **anti-war movies are a movie genre that can be linked to the time period of the Vietnam war**. This is interesting given that it is far from the only war the USA has been belligerent in, and they have also participated in many wars since.


We performed topic analysis on American war films and anti-war films to see the difference between them. The results showed that they discussed very similar topics, related to war and violence, but that war films also treated family and children which anti-war films did not. It seems like war films tend to also have side stories treating family, whilst anti-war films talk almost exclusively of the war.

### The words "Vietnam" and "War" in American movies
Do these movies only talk about the country of Vietnam in relation to the war ? To explore this, we first look at the proportion of American movie summaries that contain the word "Vietnam" over time. We do not repeat this analysis for the USSR, since there are only 2 movies made there that include the word "Vietnam" in their summary.

![Not found]({{ 'assets/img/vietnam3.jpg' | relative_url }})

As we can see, American movies did not discuss Vietnam at all before the war. We can also see that the difference between the proportion of these movies made during and after the war is not statistically significant. Suggesting that the war had a deep impact on culture and as with European movies after WWII, Americans still had to talk about the war to process the trauma. However, visually, we can see that the proportion of movies mentioning Vietnam goes down a lot after the end of the war.

We now do topic analysis on the American movies that include the word "Vietnam'' in the summary.

|Topic       	|Normalized frequency |
|:---------------|:-------------------:|
|negative_emotion|0.007            	|
|war         	|0.007            	|
|family      	|0.006            	|
|fight       	|0.006            	|
|children    	|0.006            	|
|crime       	|0.006            	|
|military    	|0.006            	|
|death       	|0.005            	|
|home        	|0.005            	|
|traveling   	|0.005            	|

From these topics, we can see that war and violence are major topics in American movies that somehow include Vietnam. Finally, we count the percentage of American movies that include the words "vietnam" and "war".
We can see that 77% of movies that include the word "Vietnam" in the summary also include the word "war" in the summary. This, along with the above topic analysis, shows us that American movies that somehow discuss Vietnam usually also discuss war, and probably discusses the Vietnam War. Similarly, of all American movies that include the word "Germany", 76% also include the word "war", and 84% include the word “war” or the word “nazi”. When discussing these countries, American movies seem to focus on the aspects of the wars that they fought with them. Inversely, only 61% of German movies that mention the USA also mention the word “war”, and for the very few Vietnamese movies in our dataset, it’s 25%.







Take home message
-----------------

War has had a significant impact on film, both in terms of the themes and genres of films produced, as well as the general feeling and perspective on war that is portrayed in these films. In our analysis, we have found that all countries’ movie industries do not react the same to a war. In some countries, like in the USSR during the Vietnam War, war films are extremely prevalent. In others, like France during the occupation that began in 1940, films almost only handle topics like romance and family and do not discuss the war. This can often be traced back to the political context of the country at that time. 



