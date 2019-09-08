# Coursera_Capstone
this is for the capstone coursera project

In this project, I will create some jupyter notebook and fulfilll the assignments in this project. 


## Capstone Project  

### Business Problem   

There are thousands of cities around the world. They are very diverse in terms of culture, economy etc. For a tourism company, to group all those popular cities into several cluster is very important. With this information, it will help client to choose the right cities to visit, especially for those tourist who want to experience different cultures.  

In this project, we will choose those biggest cities in the world (based on population) , use Foursquare API to retrieve the top popular sites in those cities and then clustering them into several clusters..  

### Data:  

1. A list of big cities in the world. We get the list from this link which contains 220+ biggest cities with largest population.  
https://en.wikipedia.org/wiki/List_of_largest_cities

1. Latitude and longitude of cities in the world. we get the information from this link:  
https://simplemaps.com/data/world-cities
In the list, it contains the city name,  latitude and longitude, country, population, time zone, ranking etc. Based on the object of this, we only the latitude and longitude of those cities. 

1. Foursquare location data   
We will use the "explore" api to get top places in each city , and then use the categories of those top places as the features, and apply the k-means algorithm to cluster those cities into groups. 
In the Foursquare "explore" api, we will use the radius 30km (300000m) as the parameter, since this are will almost cover the main area of the city. 

### Methodology: 

#### Business understanding and analytic approach
In this project, the objective is to analyze the given cities with largest population around the world and then group them together into several groups. Those groups will provide information to tourist to understand how similar those cities are and help tourist to choose tourism destination, especially helpful if they want to experience different cultures.  
There's no predefined categories, so we decided to choose a non supervised learning algorism , k-means clustering .

#### data requirements 
1. Largest cities around the world. Firstly , we need to get the name list of those largest cities. 
1. Longitude and latitude of those cities.. 
1. The top venues in those cities.. 

#### deta collection: 
1. for name list of the cities, we can get the information form this link.   
https://en.wikipedia.org/wiki/List_of_largest_cities  
1. for the latitude and longitude of those cities, we found a website can provide the information in spreadsheet. we download it and then use it in the project. 
1. The top venues. We will use "explore" api to get such information based on the latitude and longitude of those cities.. 

#### data understanding, preparation 
The list of the largest cities is based on the population..
In the latitude and longitude information for cities, I merged with the above city list so that we can get the lat and lng for those in-scope cities.. 
In the merged dataframe, I noticed that some of the cities are failed to get the lat and lng. I just discard those rows, since the remaining cities are already sufficient for me to fulfill the objective of this project. 
222 cities are in the final list and analyzed.  
In the Fourspare, we use radius as 30km to cover the main area of a city and pick the top 100 venues for us to model. 

Then I use the folium map to visulize those cities to show how those cities are distributed in the world map.

#### Modeling & Evaluation
In k-means clustering modeling, the k value is very important. I tried a few diferent values (4, 5, 6, 7, 10) and see the clustering result of those k values and I finally choose the 6 as the final result. 
 
The evaluation for a non-supervised machine learning is different from  supervised learning. By checking different k values, I checked the clustering result on the folumn map and the k=6 is of the best cluster result 


### Result: 
I got the 6 clusters in the end. Below are some interesting finding: 
1. I can see cities in North America and south America are almost in the same cluster. (cluster 3)  
1. In Asia, the groups of cities are much more diverse.  
      1. Most cities in China are in one cluster (cluster 5)
      1. Japan cities are in another cluster which are the same as America cities. This shows that Japan is more westernized that all other Asia countries. Btw, Shanghai, China is also in the same cluster as other America cities. This also matches my feeling. (cluster 3)
      1. Most India cities in cluster 2, and Asean cities are mostly in cluster 1
1. In Europe, Landon, Paris, Barcelona are of cluster 1, which is interesting, one of reason might be that those cities are of long history and popular tourism cities. (there are many hotels :) 

### Discussion : 
There are still a lot of area we can improve. you will notice that in this result, I selected must more Asia cities than America cities. the reason is because I choose the in-scope cities based on population. Usually Asia cities have much populations than other continents. 

The use the Foursquere "explore" api, there are limitation. For example, it can only retrieve at most 100 top venues in the result. This might impact the final result because some of the less popular venues in the city might be a distiguisher for that city..

Another limitation of the "explore" api is that I can only use radius as the search condition, which might be in-accurate, one issue is, if two famous cities are closed to each other, then some venues in another city might be falled into the seach result for one city (for example, I notice some venues in Hongkong falled into the search result in Shenzhen, both of them are big city and Hongkong and Shenzhen is close to each other)

To help the tourist to understand the difference of those cities. The data provided by the Foursquare might be insufficient, for example we can introduce more data such as economic data, etc.. It depends on the data availability, and if we have the data and can make use of them, then it can future improvement for this analysis.

### Conclusion: 
By use the k-means modeling, I tried to cluster over 220+ cities with largest population in the world into 6 clustering. It provide the information how those similar those cities are..  As I said in the discussion section, if we can collect more data besides the Foursquare data, then the model can be improved in the future.. 



      








