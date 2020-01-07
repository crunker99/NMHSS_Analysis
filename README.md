NMHSS 2010-2018 Survey Data EDA


Getting an overview of facility counts by state:
![Facilities by state](/images/facByState.jpeg)

Bringing in 2018 population data, notice the similarity, but also differnce:
![Population by state](/images/popByState.jpeg)

The linear correlation coefficient (r) between population and state facility count = 0.832893,
which is a relatively strong positive correlation.

Does the number of facilities, though, keep up with the population size? What are the statewide facility counts per capita?
![Facilities per 100k people by state](/images/facPerCapitaByState.jpeg)

Maine, Alaska, Vermont ... good job:

<img src="/images/topten1.jpeg" width="324" height="324">


Some states with a lot of facilities, like California and Florida, come in the bottom ten for number of facilities per population:

<img src="/images/topten1.jpeg" width="324" height="324">


```python
def grab_features(arr, features, ind, normed=False):
    selection = pd.DataFrame(pd.Series(sum(df[df[f] > 0][f]) for f in features) for df in arr)

    if normed:
        if selection.shape[1] > 1:
            selection = selection.apply(lambda x: [elem/sum(x) for elem in x], 
                                        axis=1, 
                                        result_type='expand')
        else:
            scalars = pd.DataFrame([len(df) for df in arr])
            scalars.columns = selection.columns
            scalars.index = selection.index
            selection = selection / scalars
    selection.index = ind
    selection.columns = features
    return selection
```