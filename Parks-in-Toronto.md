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

## Methodology

1. The criterion used to define "A park nearby" is the same as used during the course when the Toronto neighbourhoods where examined: It is that the distance of a park to the neighbourhood coordinates shall not be more than 500 meters in the Foursquare query.
2. The way to create the neighbourhood-parks dataframe is just the joining of the Neighbouthood- and the park-counting-dataframe.
3. For chosing the five neighbourhoods where the first new parks are to be projected, a K-Means-Algorithm with 5 clusters is used. The distance function is just the distance between the coordinates. This seems to me to be the adequate approach to have a geographical clustering in 5 areas.
4. Within the clusters, to chose the neighbourhood for the new park, the initial idea was to just take the nearest neighbourhood to the cluster centers, but looking at the map, there sometimes were green areas (which in Foursquare are not marked as parks), so the choice was changed to a neighbourhood further away from green areas.

## Results

We yield the following results.

1. As first result, we find out, that of the 103 neighbourhoods, the number of nearby parks is the following:

|\#Neighbourhoods|\#Parks|
|:-------------:|:----:|
|56|0|
|32|1|
|14|2|
|1|3|

1. The nearby-parks (at least the from Foursquare) are actually more in the center than outside.
![image](https://user-images.githubusercontent.com/62191134/113913868-250b5b80-97dd-11eb-8450-eb8aa26fa198.png)
<br>The circles represent the neighbourhood centers, the color-code is as follows:
<br>Dark green: Neighbourhood with 3 parks
<br>Light green: Neighbourhoods with 2 parks
<br>Orange: Neighbourhoods with 1 park
<br>Red: Neighbourhoods without parks

1. Clustering the neighbourhoods in 5 areas with the k-Means-Algorithm we see a quite expected distribution of the neighbourhoods.
![image](https://user-images.githubusercontent.com/62191134/113914625-09ed1b80-97de-11eb-8ccd-7d8c0113267c.png)
The big points are the cluster-centers. 

1. The choice of the 5 neighbourhoods where to start the construction of the parks is done by looking at the map. It should not be neighbourhoods near national parks etc.
![image](https://user-images.githubusercontent.com/62191134/113915081-9e577e00-97de-11eb-9e16-b23f6c588c31.png)
The chosen ones are the following neighbourhoods.
<li>Brockton, Parkdale Village, Exhibition Place
<li>Alderwood, Long Branch
<li>Bedford Park, Lawrence Manor East
<li>Guildwood, Morningside, West Hill
<li>Wexford, Maryvale

## Discussion

Maybe the limitation of the use of Foursquare gives us not all the data. One could think to find other sources to determine if there are more parks than in Foursquare. But it gives a good approximation.

Actually, I was really surprised there were so many neighbourhoods without parks.

The K-Means-Algorithm in itself did not show any surprises, the distribution of the identified neighbourhoods was quite intuitive.

The Folium-Map-library was really helpful to visualize the problem and the results.

## Conclusion

The data science methods, libraries and python abilities learned during this formation cycle were really helpful to tackle this problem. But maybe the limitation to the Foursquare web service covered up different ways for the data cimpilation.
