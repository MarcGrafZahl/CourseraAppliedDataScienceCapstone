# A Park for every neighbourhood in Toronto
by Marc Behrens

## Introdution
You are the data science consultant of a candidate who runs for the <b>mayor's office in Toronto</b>. Your boss' politics is based in an enhancement of the urban space for the people.
One of his most prominent slogans is "<b>A park in every neighbourhood</b>", promising that every citizen must have a park in his neighbourhood.

The campaign is running very well, your boss is leading the polls which he initially had not counted on. 
So, as victory is neigh, the candidate becomes more anxious about the <b>viability</b> of his political program.

He charges you with a study of <b>how many parks</b> would he have to <b>build</b> in order to keep up the promise in campaign. 

So, your task will be to gather the data of <b>how many neighbourhoods in Toronto do not have a park right now</b>.
And make a proposal, <b>where to build new parks first</b>.

## Data
We will need the following data:
1. The Toronto Neighbourhoods with its coordinates.
2. The number of parks of every Neighbourhood.
3. A map of Toronto with the neighbourhoods without parks.

The <b>Toronto neighbourhoods with its coordinates</b> is a dataframe we already have created in earlier exercises.
They were created on basis of: 
* the Wikipedia-Page 'https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M 
* a csv-file with the coordinates of the postal codes in Toronto: https://cocl.us/Geospatial_data

The <b>number of parks</b> of every neighbourhood will be taken from queries on <b>foursquare</b> for every neighbourhood, looking for <b>venues of the category "Park"</b>. 
From this data, a dataframe will be formed with the neighbourhoods and the number of parks. This dataframe will be joined with the dataframe of the Toronto neighbourhoods to identify the neighbourhoods without park.

As <b>map</b>, we will use folium to visualize the distribution of the neighbourhoods wwithout parks. 
This is important to identify the parks to be build in a first step, in order to not build them all in one spot.

## Methotology

## Results

As first result, we find out, that of the 103 neighbourhods, the number of nearby parks is the following:
|\#Neighbourhoods|\#Parks|
|:-------------:|:----:|
|56|0|
|32|1|
|14|2|
|1|3|


## Discussion

## Conclusion


