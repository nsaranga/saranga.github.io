---
layout: post
title: What Can Cricketstats Do?
date: 2021-12-24
categories: cricket
---
In the last post I explained why I decided to write [cricketstats](https://github.com/nsaranga/cricketstats) and what the aim of the module is. I said that one of the aims of cricketstats was to help data analysts in analytics projects in cricket and not statisticians. In this post I want to explain what I mean by this and say a little bit more on what the module can actually do as of now. By saying the module is for analytics projects in cricket I mean that it is meant for evaluating or predicting player and team performances in cricket rather than for compiling a database of player or team statistics. This means that rather than being able to answer a question like, "When was the last time England won a Test match at the Adelaide Oval?", the module is designed to answer a question like, "What are the averages of the current Australian batting line up at the MCG in the first 30 overs in the last three years?" For what it is worth here is the answer to that question:
|               |   Batting Avg |   Batting S/R |   Boundary % |   Balls Faced |
|:--------------|--------------:|--------------:|-------------:|--------------:|
| DA Warner     |          39.5 |         61.24 |         4.65 |           129 |
| SPD Smith     |          17   |         29.31 |         3.45 |            58 |
| M Labuschagne |         100   |         42.02 |         2.94 |           238 |
| TM Head       |           0   |         38.68 |         2.83 |           106 |
| MS Harris     |          17.5 |         57.38 |         4.92 |            61 |
| C Green       |           0   |          0    |         0    |             0 |
| AT Carey      |           0   |          0    |         0    |             0 |
| UT Khawaja    |          27   |         59.34 |         8.79 |            91 |

As that table shows, the module can produce the basic stats many of us are familiar with, eg. averages, strike rates, and economy rates. In addition it can produce the raw stats that generate those various ratios, eg. Runs, Balls Faced, Outs (including a decomposition of the modes of dismissal) and more. Importantly the module can produce those statistics for players and teams across various parameters. As we have just seen it can filter by match types, an interval of dates, an interval of overs, cricket grounds, specific tournaments, place in the batting order or bowling order.

In addition to the basic statistics above, the module can also produce some more exotic metrics as well such as, Score Mean Absolute Deviation (MeanAD), Batting Strike rate MeanAD,  Avg First Boundary Ball, Strike Turnover % for batters, and for bowlers, 'Economy Rate MeanAD, Avg Consecutive Dot Balls. The "MeanAD'' stats are a measure of consistency in that they express how much a particular statistic varies on average from the average for a player or team eg. the Score MeanAD expresses the average deviation from a player's average score in an innings in the time period searched for. I chose to involve this measure of consistency because it doesn't seem to me that all cricket statistics are gaussian distributions and as such a mean absolute deviation is probably a better measure of variance than standard deviation. Of course the module does provide the raw series of scores so a user can get standard deviations as well.

The "Avg First Boundary Ball" expresses the number of balls on average that a batter takes to hit their first boundary. The "Avg Consecutive Dot Balls" express the number of consecutive dot balls a bowler balls on average.  I provided these as they are both a measure of a particular tactic the batter or bowler will attempt in a game. The "Strike Turnover %" expresses the ratio between the number of times a batter successfully turns over the strike with a single or three on the last ball of an over. As you can imagine this is better targeted at lower order batters who are often actively trying to employ this tactic to get the established batter on strike.

Returning to the question above about Australia's batting lineup at the MCG, another thing the module can do is provide matchup data. This can allow for an analysis of how a player matches up against a particular type of batter or bowler or even against specific players. For instance, as I write this England are touring Australia and one question we might think about is how the Australian batting lineup has fared against left arm orthodox spinners in Test and domestic first-class cricket given England have one such spinner in Jack Leach. Here is what the module would produce for a query like that:
|               |   Runs |   Outs |   Batting Avg |   Batting S/R |   Boundary % |   Balls Faced |
|:--------------|-------:|-------:|--------------:|--------------:|-------------:|--------------:|
| DA Warner     |     48 |      0 |          0    |         81.36 |        10.17 |            59 |
| SPD Smith     |    178 |      1 |        178    |         57.61 |         6.15 |           309 |
| M Labuschagne |    349 |      6 |         58.17 |         74.57 |         7.48 |           468 |
| TM Head       |    379 |      7 |         54.14 |         54.69 |         5.48 |           693 |
| MS Harris     |    158 |      5 |         31.6  |         52.32 |         4.64 |           302 |
| C Green       |     67 |      1 |         67    |         69.79 |         8.33 |            96 |
| AT Carey      |     68 |      3 |         22.67 |         87.18 |         7.69 |            78 |
| UT Khawaja    |     60 |      1 |         60    |         75.95 |        10.13 |            79 |

The module can show us with the runs and outs columns a bit more about where player averages are coming from and how much to weigh their averages given how many balls they have faced. The module can produce these sorts of matchup stats for bowlers as well against specific batters and batters by handedness.

While most of the statistics the module can produce for players can also be produced for teams, there a couple that are unique to teams. For instances the module can provide a list of innings results eg. Scores, Outs, and Overs faced. It can also provide successfully defended and chased scores, Net Boundary %, and Net Run Rate. I will not explain these here as they are relatively self-explanatory.

Finally, it is worth mentioning that the full range of statistics available across all the possibel parameters can found in the "example.py" file I have provided with the module. The final provides a breakdown of how to use the module and an example for how to plot the data to create interesting visualisations of the data.


