# NMHSS 2010-2018 Survey Data EDA


Data comes from 7 years of the [National Mental Health Services Survey](https://www.datafiles.samhsa.gov/study-series/national-mental-health-services-survey-n-mhss-nid13521) (N-MHSS), "an annual survey designed to collect statistical information on the services and characteristics of all known mental health treatment facilities within the 50 States, the District of Columbia, and the U.S. territories."


### Yearly overview:

<img src="/images/totalresponses.jpeg">


#### Focus on 2018 (most recent data)

Getting an overview of facility counts by state:
![Facilities by state](/images/facByState.jpeg)

Bringing in [2018 population data](https://www.census.gov/newsroom/press-kits/2018/pop-estimates-national-state.html), we see some obvious similarities, as well as differences:
![Population by state](/images/popByState.jpeg)

The linear correlation coefficient (r) between population and facility count as a function of state is 0.832893,
which is a relatively strong positive correlation.

Does the number of facilities in a state keep up with its population size? What are the statewide facility counts per capita?

![Facilities per 100k people by state](/images/facPerCapitaByState.jpeg)

States with lower [population density](https://en.wikipedia.org/wiki/List_of_states_and_territories_of_the_United_States_by_population_density), such as Maine(46th by population denisty), Alaska(50th), and Vermont(31st) score higher. Some states with many facilities, such as California and Florida, score in the bottom ten.

<img src="/images/topten1.jpeg">



## At-risk groups and treatment availability 

I am interested in the availability of services to at-risk groups, including children, the elderly, members of the LGBT community, and veterans. Continuing with a geographic approach


#### Children

<img src="/images/children_map.jpeg">
<img src="/images/children_states.jpeg">


#### Elderly

<img src="/images/seniors_map.jpeg">
<img src="/images/seniors_states.jpeg">
<img src="/images/alz_d_map.jpeg">
<img src="/images/alz_d_states.jpeg">


#### LGBT

<img src="/images/lgbt_map.jpeg">
<img src="/images/lgbt_states.jpeg">

#### Veterans

<img src="/images/vet_map.jpeg">
<img src="/images/vet_states.jpeg">


## Comparison of CA to USA


The 2018 [survey](https://nbviewer.jupyter.org/github/crunker99/U.S.-Mental-Health-Facilities/blob/master/data/NMHSS2018DS0001infoquestionnairespecs.pdf) asked each facility if they offered dedicated services for various demographics that could be considered at-risk groups, such as children/adolescents with serious emotional disturbances, persons with a diagnosis of PTSD, veterans, 


In the USA, the highest 'score' for count of services was 17. In CA, it was 14.
Looking across the mean score of all the facilities in each state:

<img src="./images/mean_score_map.jpeg">

Lowest mean score: Iowa - 2.58
Highest mean score: Hawaii - 5.0

Overall USA mean score: 3.64
CA mean score: 3.86


<img src="./images/mean_dist.jpeg">

So California scores a little better, but how significant is the 0.22 difference in average number of services offered?

Null hypothesis: There is no signficant difference between the mean number of services for at-risk groups offered at mental health treatment facilities in California and the rest of the country.

Alternate hypothesis: The mean number of services offered at mental health treatment facilities in California is significantly greater than the rest of the country.

---
|Number of facilities in USA (excluding CA): 10829|Number of facilities in CA: 850|
|---|---|

Normalize the frequency counts to the rate they occur in each sample.

<img src="/images/prob_dist1.jpeg">

###Mann-Whitney U-statistic
Because the data was not normally distributed, I used a Mann-Whitney U-statistic to test the validity of the null hypothesis within a confidence interval of 95%.

#### p-value = 0.000000221

As the p-value < 0.05, we may <b>reject</b> the null hypothesis within the accepted range of type 1 error, using the Mann-Whitney U-test. 

Because we are ultimately interested in the averages of our samples, let's perform a T-test as well.

Calculated degrees of freedom:
