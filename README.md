# grenfell-mp-mentions-social-media
Every MP tweet and Facebook update about Grenfell during one year
http://birminghameastside.com/2018/06/14/grenfell-mp-mentions-social-media/

Coinciding with the one year anniversary of the Grenfell Tower fire on 14 June, a href="http://birminghameastside.com/2018/06/14/grenfell-mp-mentions-social-media/">Birmingham Eastside</a> decided to find out which MPs have continued to talk about the topic throughout the past 12 months on Twitter and Facebook. 

# Get the data
The data was collated with <a href="http://www.crowdtangle.com/">Crowdtangle</a> and inluded all the tweets and Facebook updates made by MPs between June 2017 and June 2018 mentioning "Grenfell" in their messages or linked content. 

The scraping provided these 4 files below: 
<ul>
  <li><a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-FB-UK---Conservatives-2017-06-06--2018-06-06.csv">CSV: Grenfell mentions by Conservative MPs on Facebook</a></li>

  <li><a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-FB-UK---Labour-2017-06-07--2018-06-07.csv">CSV: Grenfell mentions by Labour MPs on Facebook</a></li>
  
  <li><a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-FB-UK-Parliament-2017-06-07--2018-06-07.csv">CSV: Grenfell mentions by all MPs on Facebook</a></li>

  <li><a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-Tw-UK---MPs-2017-06-07--2018-06-07.csv">CSV: Grenfell mentions by all MPs on Twitter</a></li>
</ul>

# Data cleaning
To visualise the data, it had first to be cleaned. Excel formulas and pivot tables were used to put the data together and remove duplicates. 

Excel VLOOKUP formula was used to match the party of the MPs from the <a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-Tw-UK---MPs-2017-06-07--2018-06-07.csv">Twitter database</a>, comparing the names in our data to the list <a href="https://www.mpsontwitter.co.uk/list">MPs on Twitter</a>.

To match the party of the MPs from the Facebook database who only apeared in the <a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell-mentions-FB-UK-Parliament-2017-06-07--2018-06-07.csv">Parliament list</a>, the Wikipedia <a href="https://en.wikipedia.org/wiki/List_of_MPs_elected_in_the_United_Kingdom_general_election,_2017">List of MPs elected in the United Kingdom general election, 2017</a> was used. 

In the second case, names had to be cleaned, as most of the MPs add other words like "MP" or their party at the end of the profile name. The following is an example of a formula used to clean the "MP" bit at the end of the profile name: 

```
=IF(ISERR(FIND(" MP",A2)),A2,REPLACE(A2,FIND(" MP",A2),3,""))
```

# Analysis
After cleaning, some analysis needed to be done to know when and by who the mentions were made the most. 

The month and the year of the message were extracted with their respective MONTH and YEAR formulas and put toghether with a CONCATENATE formula to create a new column grouped and ordered by each of the 12 months.

Also, we were interested in the mention of Grenfell in relation to debates like materials in use in tower blocks in general. That is why the formula <em>=SEARCH("cladding",A2)</em> was used to find out a 10% of the messages also mentioned the word "cladding".

Because of our West Midlands focus, we matched these region's MPs to their constituencies using, again a VLOOKUP formula. 

The clean data with the new calculated variables can be downloaded from <a href="https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Grenfell%20mentions%20-%20all%20clean.csv">this CSV</a>.

# Visualisation
We used the survey template from <a href="https://flourish.studio/">Flourish studio</a> to create the interactive visualisation.

In <a href="https://public.flourish.studio/visualisation/60375/">this visualisation</a> the user can group, colour and compare by party, date and platform. Hovering over the dots, which represent each tweet or Facebook update, details of the MP, the party, the day and the message appear. 

![Grenfell mentions](https://github.com/Birmingham-Eastside/grenfell-mp-mentions-social-media/blob/master/Visualisation%20-%20Grenfell%20mentions.png)

