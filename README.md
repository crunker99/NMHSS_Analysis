# NMHSS 2010-2018 Survey Data EDA


Data comes from 7 years of the [National Mental Health Services Survey](https://www.datafiles.samhsa.gov/study-series/national-mental-health-services-survey-n-mhss-nid13521) (N-MHSS), "an annual survey designed to collect statistical information on the services and characteristics of all known mental health treatment facilities within the 50 States, the District of Columbia, and the U.S. territories. In every other year, beginning in 2014, the survey also collects statistical information on the numbers and demographic characteristics of persons served in these treatment facilities as of a specified survey reference date."


Yearly overview:

<img src="/images/totalresponses.jpeg">


Getting an overview of facility counts by state:
![Facilities by state](/images/facByState.jpeg)

Bringing in [2018 population data](https://www.census.gov/newsroom/press-kits/2018/pop-estimates-national-state.html), notice the similarity, but also differnce:
![Population by state](/images/popByState.jpeg)

The linear correlation coefficient (r) between population and state facility count = 0.832893,
which is a relatively strong positive correlation.

Does the number of facilities, though, keep up with the population size? What are the statewide facility counts per capita?
![Facilities per 100k people by state](/images/facPerCapitaByState.jpeg)

We find that states with lower [population density](https://en.wikipedia.org/wiki/List_of_states_and_territories_of_the_United_States_by_population_density)  score better, such as Maine(46th by population denisty), Alaska(50th), and Vermont(31st).

<img src="/images/topten1.jpeg">


Some states with a lot of facilities, like California and Florida, come in the bottom ten for number of facilities per capita:

<img src="/images/bottomten1.jpeg">



## At-risk groups and treatment availability 

I am interested in the availability of services to at-risk groups, including children, the elderly, members of the LGBT community, and veterans.



### Children

Coastal cities appear to offer less mental health care for children.
<img src="/images/child_h.jpeg">

<img src="/images/child_l.jpeg">

<img src="/images/child_by_state.jpeg">




### Elderly




### LGBT

Where are dedicated LGBT services commonly offered?


<img src="/images/lgbt_h.jpeg">

<img src="/images/lgbt_l.jpeg">

<img src="/images/lgbt_by_state.jpeg">


### 

