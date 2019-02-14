## Data

The data for this project was collected from 3 main sources: Wikipedia, [geopy](https://geopy.readthedocs.io/) python package and [Foursquare](https://foursquare.com/). The list of New York neighborhoods was first obtained from Wikipedia, geographic co-ordinates for each neighborhood for each neighborhood was obtained using geopy and the details of restaurants located in each neighborhood were fetched using the Foursquare API.

The names of the neighborhoods were obtained from the wikipedia page, [Neighborhoods in New York City](https://en.wikipedia.org/wiki/Neighborhoods_in_New_York_City). The data was available in an HTML table with the New York community board names, area, population and neighborhoods in each board.

![Figure 1: HTML table from wikipedia](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%201.png)
##### Figure 1: HTML table from wikipedia

<br />

The table data from Figure 1 was scraped using the [BeautifulSoup](https://pypi.org/project/beautifulsoup4/) python library. The scraped data was then cleaned and stored in a pandas dataframe. The borough names were extracted from the community board name and included as a new column.

![Figure 2: Scraped data in a pandas dataframe](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%202.png)
##### Figure 2: Scraped data in a pandas dataframe  

<br />

Next, neighborhoods from Manhattan were extracted and the geographical coordinates for each of them were fetched using the geopy python package.

![Figure 3: Location data for neighborhoods](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%203.png)
##### Figure 3: Location data for neighborhoods  

<br />

To get the list of restaurants and their details, the Foursquare API was used. The explore, venues and search API endpoints were used. The following figure shows the JSON response of the explore endpoint for a single neighborhood.

![Figure 4: JSON response for the Foursquare API's explore endpoint](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%204.png)
##### Figure 4: JSON response for the Foursquare API's explore endpoint

<br />

The explore endpoint was used to fetch restaurants around a 500 metre radius of each Manhattan neighborhood. The names of each restaurant, their geographical coordinates, address and categories were extracted from the response and stored in a dataframe.

![Figure 5: Restaurant data](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%205.png)
##### Figure 5: Restaurant data

<br />

The price tier, ratings, rating signals, tips likes, features for each restaurant were fetched using the venues endpoint of the API.

![Figure 6: Restaurant Details](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%206.png)
##### Figure 6: Restaurant Details

<br />

The closest venues around each restaurant were also fetched to understand how they affect restaurant ratings and reviews. The search endpoint of the API was used to find venues around a 250 metre radius of each restaurant. The response included the distance of each venue from the restaurant. Only the 10 closest venues were chosen based on the distance value.

![Figure 7: 10 closest venues around restaurants](https://github.com/perlypin/Coursera_Capstone/blob/master/NY_Restaurant_Analysis/report/Figure%207.png)
##### Figure 7: 10 closest venues around restaurants

<br />

The restaurants details were used to segment the restaurants into clusters. Each cluster was further analyzed along with venues around each restaurant to understand how it may affect restaurant ratings and reviews.
