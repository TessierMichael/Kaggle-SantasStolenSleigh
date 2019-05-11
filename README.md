# Santa's Stolen Sleigh

## Description

The North Pole is in an uproar over news that Santa's magic sleigh has been stolen. Able to carry all the world's presents in one trip, it was considered crucial to successfully delivering holiday goodies across the globe in one night.

Unwilling to cancel Christmas, Santa is determined to deliver toys to all the good girls and boys using his day-to-day, magic-less sleigh. With so little time to pull off this plan, Santa is once again counting on Kagglers to help.

Given the sleigh's antiquated, weight-limited specifications, your challenge is to optimize the routes and loads Santa will take to and from the North Pole. And don't forget about Dasher, Dancer, Prancer, and Vixen; Santa is adamant that the best solutions will minimize the toll of this hectic night on his reindeer friends.

## Evaluation

Your goal is to minimize total weighted reindeer weariness:

Mathematically, weighted reindeer weariness is calculated by:

$WRW=\sum^m_{j=1}\sum^n_{i=1}\left[\left(\sum^n_{k=1}w_{kj}-\sum^i_{k=1}w_{kj})\cdot Dist(Loc_i,Loc_{i-1}\right)\right]_j$,

where $m$ is the number of trips, $n$ is the number of gifts for each trip $j$
, $w_{ij}$ is the weight of the $i^{th}$ gift at trip $j$, $Dist()$ is calculated with Haversine Distance between two locations, and $Loc_i$ is the location of gift $i$. $Loc_0$ and $Loc_n$ are North Pole, and $w_{nj}$

, a.k.a. the last leg of each trip, is always the base weight of the sleigh.

For example, if you have 2 gifts A, B to deliver in the trip, then the $WRW$ is calculated as:

dist( North pole to A ) * ( weight A + weight B + base_weight ) +
    dist( A to B ) * ( weight B + base_weight ) + dist( B to North pole ) * ( base_weight )