# ADS-B 

## Getting nerdsniped[^nerdsniping]

No matter how much you know about a subject, there are always times when you stumble upon a random product which makes you wonder - "how the _heck_ does that thing work ?!".  

One occurence of that phenomenon I have experienced was with websites like [FlightRadar24](https://www.flightradar24.com/), [FlightAware](https://www.flightaware.com/) or [adsb.fi](https://adsb.fi/). It is not the way the map is displayed that was peeking my interest (plenty of other mapping sites do it, using [Openstreetmap](https://www.openstreetmap.org), [Mapbox](https://www.mapbox.com/), or [Google Maps](https://maps.google.com/) APIs), but rather the question of _how do they know where the planes are ?_


## Looking for the answer

Often, the rabbit hole starts with a simple search and, sometimes, comes out as obvious : I remember in my childhood days, the time someone told be how an electrical switch worked. A simple drawing was sufficient. When it is not the case, however, the search can become a journey full of discoveries. It is armed with patience and humility that I wandered in the intersection of aviation and telecommunications. 


## Diving into it


The main question related to the flight activity websites was how had the data gathering process taken place ? It turns out that sites like this are possible thanks to hundreds of volunteers collecting data in their respective geographical areas, and sending them to the site admins, who then do the aggregation, displaying, and serving. The usual deal is that volunteers have access to the pro version of the sites since, yes, the major ones restrict access to publicly[^geo-public] available information.

So now the source of the flight data has been refined a bit. We still have to understand how those volunteers gather the data. 


It turns out that in the last decade or so, there has been an international effort to create an amazing aviation standard called ADS-B. This is a system by which all -legally compliant- aircraft is required to broadcast a 1090MHz radio signal containing their geographical coordinates. This signal being unencrypted (and its specification being public) means that anyone listening will be able to decode the information sent out _by the planes directly !_ That listening is done by creating an appropriate receiving antenna, which can be built [using hardware store components](https://lucsmall.com/2017/02/06/making-antennas-for-1090mhz-ads-b-aircraft-tracking/). 


While idle, the elementary particles called electrons contained in the antenna vibrate around their position but don't travel that much. This is why touching a copper wire which is not plugged to anything is perfectly safe. In the presence of an _electric field_ whose strength varies in time though (there's no need to exactly understand what an electric field is at this stage, advanced readers might want to look it up), the electrons will start to oscillate with greater amplitude, creating an electric current. This is an interesting propery since the waves emitted by the aircrafts carry an electric field : the waves travel through the air, from the plane to the antenna. And because they are broadcast every second, the antennae do not have to _request_ the information, they can _listen_ to it, which means that they will be able to transform that wireless signal into a wired current in a passive way. That current is finally processed by a computer which has the ADS-B decoder tools and software needed to extract the data carried by the signal. Since the information embedded in it is quite time-sensitive, the way the data is encoded into the signal is by making use of [Pulse Position Modulation](https://en.wikipedia.org/wiki/Pulse-position_modulation).

After processing and extracting the data, it is sent over to the website operators using traditional means and, as several volunteers spread around the globe gather the data (antennae have a limited range), the data can be aggregated, cross-checked if needed, but most importantly displayed for the world to see !


## Discovering a new hobby

The joyful aspect of this is that because all the elements of the chain of the data collection are publicly available and affordable, anyone setup a listening station and share their observations with other enthusiasts. A similar system called [AIS](https://en.wikipedia.org/wiki/Automatic_identification_system) is used for maritime traffic and it may be a cool project to create an aggregator for both ADS-B and AIS.


## Sharing it with the world

This small article was written as part of my application to the [Ethereum Protocol Fellowship 5](https://blog.ethereum.org/2024/05/13/epf-5-announcement), with the instructions being to "write an essay explaining a technical topic". I hope you have found it insighful and instructive, regardless of your technical and scientific background.

Sileo.


[^nerdsniping]: From the [Wiktionary](https://en.wiktionary.org/wiki/nerd-snipe#English): "To present someone with a very interesting problem to solve, distracting them from whatever they were doing previously."
[^geo-public]: More specifically, publicly available info, _if in the appropriate geographical location_

