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
From this data, a dataframe will be formed with the neighbourhoods and the nuumber of parks. This dataframe will be joined with the dataframe of the Toronto neighbourhoods to identify the neighbourhoods without park.

As <b>map</b>, we will use folium to visualize the distribution of the neighbourhoods wwithout parks. 
This is important to identify the parks to be build in a first step, in order to not build them all in one spot.
