# Project Title: Communicate Data Findings from the Ford GoBike System Data
### by Thárcyla Mourão

## Dataset

Ford GoBike was a bike-sharing system that covered the greater San Francisco Bay area from [2017](https://media.ford.com/content/fordmedia/fna/us/en/news/2017/06/27/ford-gobike-launching-in-bay-area-bike-sharing.html) to [2019](https://techcrunch.com/2019/06/11/lyft-deploys-its-pink-wheeled-bikes-and-rebrands-ford-gobike-as-bay-wheels/). This dataset has information on trips taken on February 2019. 

Among the information available in the dataset, I had start time, end time, names of the start and end stations, gender, birth year of users, among others.

The objective of this project was to create a series of exploratory and explanatory visualizations related to my main variable of interest, **trip duration**. The first part covered the exploratory charts, while the second part covered the explanatory data visualizations.

Before delving into them, I had to do some preliminary data wrangling. I imported the necessary libraries and did some data cleaning, including dropping null values, converting some columns from float to ints, others from object (string) to categorical dtype, the dates from object to datetime, and one column from oject to bool. Finally, I dropped a few columns that I felt wouldn't be as useful in analysis, such as latitude and longitude for start and end stations. All of these steps were crucial to the visualizations moving forward.

## Summary of Findings

#### Univariate Exploration

In the *Univariate Exploration*, although I had my eyes on trip duration, I checked the distribution of most of the remaining columns. Interesting findings:

- Trip duration had a highly skewed distribution that benefitted from a logarithmic transformation on the x-axis. Most of the trips on this dataset took between 300 and 1000 seconds, i.e., between 5 and 15 minutes.
- I created another column, age, subtracting the year the trips were recorded in the dataset (2019) from each birth year. From there, it became clear that most users are between 18 and 40 years old.
- Plotting the number of trips per hour, we can see a bimodal distribution, with peaks at 8am and 5pm, probably representing commuter traffic.
- As far as the user type distribution goes, 9 out of 10 trips were from subscribers, which might indicate users consider the service one of their main means of transportation. Only 1 out of 10 is a customer without a subscription, which might come from more casual users or tourists.

From this section, I added the trip duration distribution plot to my explanatory presentation.

#### Bivariate Exploration 

In the following section, *Bivariate Exploration*, I mainly explored the relationship of the variables against trip duration, my main variable of interest. Comments:

- When I used start hour and trip duration, I noticed longer trips tend to happen at later hours. Then, I had the idea to make a transformation and use total travelled time instead. When I did that, a bimodal distribution appeared, with peaks at 8am and 5pm. Also, interestingly enough, during late morning to mid-afternoon, total travelled time by hour hits a plateau, until it picks up again at around 4pm.
- Once I created a scatterplot of trip duration and age, it's clear most trips were taken by people in their 20s to 40s, which was then confirmed by the heat map I plotted using those two variables.  
- While investigating the relationship between age and trip duration, I also tried plotting age against the total travelled time. Once I did that, I noticed 30-year-old people spent the most time on a bike, a little more than 2,000 hours total.
- I did a violin plot and a box plot of the relationship between trip duration and gender. Once I did that, I noticed the trip duration for non-binary users is more evenly distributed than males and females. Female and male trips tend to be around 10 minutes or so. Also, longer trips that take from 25 to 35 minutes are more common among females than males. 
- Moving away from my main variable of interest for a bit, I plotted a heat map to investigate te relationship between age and start hour of trips. The plot shows what we've established before, both the fact that most trips were taken by people in their 20s to 40s, also that the peaks are at 8am and 5pm. What was interesting was that at the very early hours of the day (before sunrise), we can also see trips from younger people, which might indicate they use the bikes after a night out as well.

From this section, I have chosen to include in my presentation the heat map of trip duration by age.

#### Multivariate Exploration

Finally, in the last section, *Multivariate Exploration*, I tried to see the relationship between trip duration and two other variables. Comments:
- From the point plots, we see more clearly that when compared to men, women take slightly longer trips. Also, for non-binary individuals, the average trip is slightly longer for both user type groups, when compared to males and females. Finally, overall, casual customers tend to take longer trips than subscribers.
- From the box plot, we can see that the distributions for subscribers has less variability than customers', for every gender.
- During the rest the day, males' and females' average trip duration is somewhat stable, with an increase from early morning to late afternoon.
- Using a subset of the data to reduce overplotting, I did a scatter plot of age vs. trip duration, with different markers for user type. In this chart, it was interesting to see that older people apparently prefer to be a subscriber instead of customer, but this warrants further investigation.
- Another interesting find was that non-binary people enjoy longer trips during the earlier hours of the day (from 1am to 4am), with smaller peaks at other times of the day. This could be seen in the last chart, where I plotted the relationship between hour vs. average trip duration, with different lines for every gender. There is also a modest peak from females during the same time period, which might suggest they'd rather grab a bike after a night out than walking home, but that assertion would require further investigation as well.

From this section, I included in my presentation the line plot of average trip duration by hour, for every gender.

## Key Insights for Presentation

For the presentation, I focused on what factors influence trip duration. I started the presentation with a histogram for the trip duration distribution given its importance to this project. From this plot, we can see that most trips take between 300 and 1000 seconds, i.e., between 5 and 15 minutes.

Then, I moved on to a heat map illustrating the relationship between trip duration and age, given that analysis showed that most of the trips were taken by people in their 20s to 40s. The plot also showed that most of the trips in that age bracket are trips with less than 1,000 seconds (around 15 minutes).

I finished the presentation with a line plot of the average trip duration by hour, for every gender. In this plot, we can see that non-binary people enjoy longer trips during the earlier hours of the day (from 1 a.m. to 4 a.m.), with smaller peaks at other times of the day. In addition to that, there is also a modest peak from females during the same time period. This might suggest they'd rather grab a bike after a night out than walking home, but that assertion would require further investigation. During the rest of the day, their average trip duration is somewhat stable, with an increase from late morning to late afternoon. Finally, males also present an even smaller peak during the same time period, but for the most part, their average trip duration remains more or less stable during the whole day.