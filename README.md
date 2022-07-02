# The Case for H3Geo and Bio-regional Eco-addressing 
### ***by Thomas Cal - October 2021 Greenpaper / Greenpill ***

The planet can be mapped with a grid of hierarchical hexagons that is useful for geo locating specific places with less distortion then other methods
why hexagons and not squares: [here](https://pro.arcgis.com/en/pro-app/latest/tool-reference/spatial-statistics/h-whyhexagons.htm) 

![](https://i.imgur.com/EtKABr0.png)

H3 geo is a hierarchical grid system which was created by [Uber engineering](https://eng.uber.com/h3/) inspired by [Buckminster Fuller](https://en.wikipedia.org/wiki/Buckminster_Fuller) using an icosahedron projection  of the earth rather than the mercator projection.  It has later been embraced by many mapping projects (see references below)

![](https://i.imgur.com/8AXK9FL.png)

The icosahedron has 20 faces and twelve vertices.
mapping is done in a way such that all vertices are in the ocean.
the vertices are pentagons and have a slight variation in their addressing scheme

![](https://i.imgur.com/6bFokrK.png)



## Address systems

Table of Cell Areas for H3 Resolutions (ref:[h3 table](https://h3geo.org/docs/core-library/restable))


| H3 resolution | Average Hexagon Area (km2) | Average Hexagon Edge Length (km) | Number of unique indexes |
| -------- | -------- | -------- | -------- |
| 0 | 4,250,546.8477000     | 1,107.712591000     | 122 |
| 1 | 607,220.9782429     | 418.676005500     | 842 |
| 2 | 86,745.8540347     | 158.244655800     | 5,882 |
| 3 | 12,392.2648621     | 59.810857940     | 41,162 |
| 4 | 1,770.3235517     | 22.606379400     | 288,122 |
| 5 | 252.9033645     | 8.544408276     | 2,016,842 |
| 6 | 36.1290521     | 3.229482772     | 14,117,882 |
| 7 | 5.1612932     | 1.220629759     | 98,825,162 |
| 8 | 0.7373276     | 0.461354684     | 691,776,122 |
| 9 | 0.1053325     | 0.174375668     | 4,842,432,842 |
| 10 | 0.0150475     | 0.065907807     | 33,897,029,882 |
| 11 | 0.0021496     | 0.024910561     | 237,279,209,162 |
| 12 | 0.0003071     | 0.009415526     | 1,660,954,464,122 |
| 13 | 0.0000439     | 0.003559893     | 11,626,681,248,842 |
| 14 | 0.0000063     | 0.001348575     | 81,386,768,741,882 |
| 15 | 0.0000009     | 0.000509713     | 569,707,381,193,162 |

***averages are given because hexagon mapping is still subject to some distortion**

We can see from the table above the number of hexagons at each resolution with average areas / sizes. Each hexagon is uniquely addressed with a 64-bit integer eg **85283473fffffff** 
This is not the most user friendly way to reference a place

An organisation called [Placekey](https://www.placekey.io/) has designed an addressing scheme based on h3 called what@where
![](https://i.imgur.com/p7O9MKn.png)
Personally I still dont find this very user friendly

## Ecological address

Imagine if people had more than an address to recieve postal mail or building entrance..
But they also had an address (or list of addresses) where they were able to do eco-restoration, tree planting etc... The address could reflect an area that the average person could manage.. what could that address look like?

| earthcell(0-121) | bioregion(0-6) | word1 | word2 |
| --------------- | ---------------- | ------------------- | ------------------- |

So if we use a baseline of resolution 11 an address like **28.2.green.farm** could represent a hexagon of land roughly **2150m2 (50m width)** in size.  smaller denominations are possible with additional grid resolutions.  For example if you have less than resolution 11 size of stewardship, then your address could be **28.2.green.farm.4** where the last digit is a subcell (0-6) This would mean an area of approximately **300m2 (19m width)** and so on until the highest resolution 15 (1m width).
without the word references the address is a less human friendly and looks something like this: 28.2.1.2.3.4.5.6.1.2.3.4 (resolution 11)

| H3 resolution | Average Hexagon Area (m2) |  Average Hexagon width (m) |
| -------- | -------- | -------- |
| 8 | 737327.6          | 922.7 |
| 9 | 105332.5         | 348.75 |
| 10 | 15047.5         | 131.82 |
| 11 | 2149.6        | 49.82 |
| 12 | 307.1         | 18.83 |
| 13 | 43.9        | 7.12 |
| 14 | 6.3         | 2.697 |
| 15 | 0.9         | 1.0194 |



## Address words (hexagon naming)
The number of permutations with two words is in the billions, especially if different languages and numeric combinations are allowed.
The two word permutation should be unique to the bioregion, the bioregion being the first two parts of the address eg. 28.2. This gives us a need for 282,475,249 unique permutations at **resolution 11** allowing for relatively short words and omission of obscure words. On top of the word permutation limit, It could be the case that addresses are proposed by the land steward/owner and awarded by a governing regeneration body on a FCFS or FIFO (first in first out) basis. The API for the address system would be easily accessible via decentralized cloud storage.

## Eco-area mapping
![](https://i.imgur.com/kM1p0ni.png)

Ideally we want the regeneration area to fit inside our eco-address, with H3 we can map a region using a range of resolutions thus limiting the amount of hexagons used. We can create a project to mapping region lookup database. 



## References
why do we need a better way to geo locate https://www.geospatialworld.net/blogs/its-time-to-agree-on-a-universal-location-standard/
https://h3geo.org/
- Roberto Valenti for giving me the initial guidance and motivation to follow through on this work

## Regen mapping
https://deck.gl/docs/api-reference/geo-layers/h3-hexagon-layer
https://map.half-earthproject.org/
https://www.restor.eco/
https://www.space4good.com/

## Tools
https://www.calculator.net/permutation-and-combination-calculator.html?cnv=44000&crv=2&x=70&y=27
https://www.omnicalculator.com/math/hexagon#honeycomb-pattern-why-the-6-sided-shape-is-so-prevalent-in-nature
