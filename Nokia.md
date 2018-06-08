# Nokia Challenges

## On demand wireless service placement
### Description
find the proper location of a WiFi access point in a radio environment with interference. One remotely controled vehicle can be used for the placement and a second one for measurements. This mimics the radio head placement and coverage measurement with drones. The teams should be able to make an algorithm which measures the radio conditions and make decision on WiFi access point location accordingly in order to achieve the best possible throughput performance on a WiFi channel. 
### Challenge
People mobility, especially in case of ad hoc events (concerts, sports, etc.) causes demand peak in ceratain locations. Extra service limited in time and location is needed to keep user statisfaction. Common approach is to place extra radio heads with drones for the time of the event. A special challenge is how to place the radio heads (without prior coverage planning) in an optimal way from coverage PoV. Existing radio heads might create interference, whereas measurements and placing has to be done on the location within short time, almost in an ad hoc manner.
### Given asset
Wifi access point with open wrt and measurement device (Android)
Remote controlled vehicles with programable API
### Required competence
Linux programming
Android programming
## Extandable object recognition system
### Description
Object recognition algorithm to be developed for a specific type of yet unknown object. 
### Challenge
Trained object recognition algorithms are commonly available with the predefined list of recognized objects. Providing simple/efficient means to extend the list of recognized objects with limited training data is the challenge.
### Given asset
Laptop with trained object recognition algorithm
tensorflow API 
### Required competence
Linux
Python
Tensorflow 
## Information spread in social network
### Description
A Tweet is going to spread in the follower network in time having several re-tweeting on the same message while it reaches maximum number of followers. Some echo may help to reach more followers, some may not, so the main impacted population is changing based on the source tweet. To understand better the information spread, a type of tweet should be analyzed and understand main impacted population and maximum tweet activity in a time interval.  
### Challenge
The quantification of the impact of  a Tweet, e.g., reach (re-tweets/time window, number of recipients)
### Given asset
Laptop
Internet connection
### Required competence
javascript
web api
analytics
## Container and Virtal Machine ecosystem
### Description
Computation intensive mobile applications require server side support. Application servers are deployed over clouds. For proper user experience (e.g. low latency, short reaction time in multi user gaming) servers must be located in the proximity of the users. In case of  mobile users, their locations are not fixed, sesssion can be originated over the whole service area, thus the server placement has to follow the demand in an ad hoc manner without much latency and by maintaining service continuity. Additional challenge is imposed by the handovers in case of users who are travelling or moving around. In case of multi-user applications, the number of users can increase/decrease dynamically thus servers resources should follow. 
### Challenge
* provide an alogrithm for optimal server location for given topology (network, cloud) with random user location considering the possible suboptimal location in case of handovers. The location of the server should be closest possible to the users
* provide a dynamic scaling method of the containers hosting the servers.  
### Given asset
computers, topology, information, docker, topology model, SimCity
### Required competence
Linux
Docker
## 
### Description
Smart public transport will have an important role in future smart cities. Identifying travel routes, the way of transports used by travelers is crucial to support route planning and public transport optimization use cases. Collecting crowd travel data (data collected by individual commuters with their mobile devices) and analyzing them provides a chance to determine the travelling behaviors of the masses. Nokia has developed an Android client that collects travel related information from friendly users’ mobile devices (e.g. location related KPIs, motion sensor data) that is uploaded and stored in a backend server. These device logs together with the Budapest public transport information (available through open APIs) will be used for the challenge.
### Challenge
* Find out the way of transport (which bus/tram lines used…) from the travelers’ logs. Map the offline, user collected mobile device sensor logs with BKK travel information gathered from BKK API. Create an analytical model for transport type prediction.
* Find out bus/tram stops from the travelers’ logs. Create an analytical model for predicting bus/tram stop locations.
### Given asset
wifi internet connection, offline data set for motion sensor logs, description of the Budapest public transport APIs
### Required competence
web API usage, data mining, analytics skills, “R” or python programming skills