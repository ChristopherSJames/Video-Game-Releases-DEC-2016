# Video Game Sales Analysis
## by Christopher James


## Dataset

This dataset contains sales statistics on video games released from 1980 through 2016. These statistics include sales numbers for North America, the European Union, Japan, and all others, the platform they were released for, the publisher, the content rating, and others. It also contains metacritic ratings and user ratings from games released starting in 1999. It has a total of 16,712 video games. This dataset can be found [Here](https://www.kaggle.com/rush4ratio/video-game-sales-with-ratings).

The following wrangling was done to the dataset:
1. There were 2 rows that were missing names, ones of which was also missing many other attributes. They were at indexes 659 and 14246. Since there was no way to tell what this data was, I deleted the 2 rows.
2. There were 4 rows that contained games that were released after 2016. They were at indexes 5936, 14086, 16222, and 16,385.  Since this dataset is only supposed to contain games released up until the end of 2016, this mistake must have been made during the web scraping process. I then deleted the 4 rows.
3. The column name 'User_Score' was of the datatype 'object'. In order to convert this to a float, I also had to deal with the 2506 rows that contained the string 'tbd'. In order to do this, I used the function 'to_numeric', and forced all non-number columns to be converted to NaNs via the 'coerced' argument.
4. I found that within the subset of the columns 'Name', 'Platform', and 'Year_of_Release', there were 2 duplicated rows. The first was the index 14246 that was removed during the cleaning of assessment 1. The second was the index 16233. I removed the second row.
I then stored the cleaned dataframe into a csv file called 'Video_Games_Sales_as_at_22_Dec_ 2016_master.csv'.



## Summary of Findings

The North American sales distribution started out at slightly above 500 and stayed there until getting past roughly 30k copies sold. The peak occurs between 100k and 300k copies sold, before rapidly descending until the 10 million sold mark.
The European Union Sales distribution started out quite high with many games selling between 10k and 30k copies. The peak her occurs between 30k and 100k copies sold, before falling through the 10 million sold mark Also notable here is that video games as a whole seem to be less popular in Europe even though the population roughly equal to the North Americas.
The Japenese sales distribution, like the EU, starts out on an elevated level before falling and then peaking between 30k and 100k sold, before falling through the 10 million sold mark.
The sales of all other countries have very different characteristics. The distribution is right skewed even when plotted on a log scale. It peaks at 10k sold and drops until it reaches 3 million sold.
There are no games here so bad that they get Metacritic ratings of 0-10. Starting at 10, there is a fairly rapid rise in the ratings distribution until it peaks between 70-80. One note of interest is the rapid decline from 80-90 to 90-100.
The distribution of user scores mostly follows the one for critic ratings, at first slowly rising then rapidly rising until peaking between 7-8. One important diference here is that the ratings for 8-9 are virtually as large, making the fall to 9-10 an even bigger drop.
The distribution of releases by year illustrates the increasing popularity of video games over the last 36 years. One point of interest here is the decrease in the number of games released after the peak in 2008.
Platforms that did not succeed had the lowest number of releases. The PS2 and the DS sold the most hardware of any system ever released, which is why more publishers would want to release games for those systems. Please note that the PS4 and The XOne were released at the end of 2013, which would explain the low numbers for them.
Action and sports are the 2 genres with the most game releases. It will be interesting to explore the possible coorelation between number of games and sales numbers.
Games rated 'E' are the most common, followed by 'T'. The 'E' rating was implemented in 1998 while 'E10' was in 2005. The 'E' rating replaced 'K-A', whose ratings are not available. 'RP' is given to games who have yet to be rated. Here, it appears there are a few that never were.
Despite the fact that most of the high sellers are in the top 50% of Metacritic scores, the same is also true for the majority of all games. This is true for all regions. There appears to be little cooreleation between sales numbers and Metacritic scores. I do not believe this warrants any further investigation.
Much like with the Metacritic score, there appears to be little to no coorelation between user score and sales numbers. Gamers are no more likely to base their buying decisions on the opinions of their peers than they are professional critics. Also like the metacritic score, this does not warrant further investigation.
In North America and the European Union, rated 'M' games have the highest mean sales, while 'EC' has the lowest. In Japan, the highest is 'E', while the lowest is 'M'. In all other regions, the highest is 'M', while the lowest is 'EC'.
In North America, the two platforms with the highest mean sales are the NES and the GB, both Nintendo systems, while the two lowest are the psp and the psv, both Sony handhelds. In the European Union, the two highest are the GB and the GEN, while the two lowest are the 2600 and the GC. In Japan, the two highest are the NES and the GB, while the two lowest are the XONE and the PCFX. In all other regions, the two highest are the GB and the PS4, while the two lowest are the XB and the 2600.
In North America, as well as the European Union, the two genres with the highest mean sales are platform and shooter, while the two with the lowest are adventure and strategy. In Japan, the two highest are platform and puzzle, while the two lowest are shooter and adventure. In all other regions, the two highest are shooter and action, while the two lowest are adventure and strategy.
The Nintendo systems, which are the GBA, the GC, both Wii models, and both ds models, have the highest mean sales in games geared towards younger players, with the ratings 'EC', 'E' and 'E10'. The Microsoft systems, which are the 3 Xbox models, along with the Sony systems, which are the 4 playstation models and the 2 portable playstation models, have higher mean sales numbers in games geared towards older players, with the ratings 'T' and 'M'. These findings are true in all of the regions.
In North America, as well as the European Union and all other regions, the top selling rating for the role-playing, shooter, and action genres is 'M'. In Japan, this rating is much less prevailent, while the 'E' rating dominates.




## Key Insights for Presentation

For the presentation, I focused how features like platform, content rating, platform, and genre would affect sales numbers. I started out showing the relationship between sales numbers and the content rating of games. Then, I showed the relationship between platform and sales. Then, I showed the relationship between sales and genre. Then, I showed the relationship between rating, plarform, and sales numbers. Finally, I showed the relationship between rating, genre, and sales numbers.