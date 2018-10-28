# Sofia: Social Fire Alarm

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/images/logo.jpg)

### Reduce the time needed for detecting fires using social networks scraping supported by AI decision making, and a mobile App where users can report alerts directly. APP includes gamification encouraging people to participate.

## 1. MOTIVATION
Each year, 340 million hectares of vegetation around the world are destroyed or degraded by fire. These fires not only alter the structure and composition of forests, but also can open up forests to invasive species, threaten biological diversity, alter water cycles and soil fertility, and endanger the people who live in and around them.  
NASA Space Apps Challenge shows us how NASA has strived to reduce the time of early detection of fires using satellite information. However, the general public or local authorities may not be able to use this information effectively.


## 2. OBJECTIVE
Our spatial mission consists in reducing the time needed for detecting fires, being helped by people even without them knowing it.  
To achieve this, the use social networks scraping, detecting fire or dangerous situations in real time. In addition to that, we have created a mobile App where users can report alerts directly, see valuable information, etc.  
This mobile App also contains a collaborative tool that includes gamification, and supports decision making for AI. With this, we encourage people to participate on this prevention tool, creating fire risk consciousness.


## 3. DESCRIPTION
The sections of the project are described below:
 
![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/diagrams/SofiaSummary.jpg)

### Data Sources
We filter social networks posts that can help to prevent and to warn about possible fires. We also obtain information from NASA and other satellites to evaluate globally fire risk areas.

### Data Processing
*	We implemented a Fire Risk Model based on satellite images to categorize the level of risk at a global level.
*	We analyze texts and images coming from social networks, applications and volunteer collaborators through our public API
*	We collect social data such as population density

### Decision Model
Combining the previously processed data, a decision model based on Machine Learning decides whether to issue an alert. This model is enforced by the community supervision through gamification (see app) for feedback and retraining.

### Alerts Dissemination
In the event of a fire alert validated by the model and an authority, it will be communicated:
*	To the global alert system corresponding to the affected area.
*	Through SMS to telephone users close to the area through the following channels local telephone companies, as long as they offer their collaboration.
*	To users of the Collaborative APP in the affected area
*	To users subscribed to RSS such as Alexa, Google Assistant, Siri, Cortana, etc.

### APP

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/images/APP%20Mockup.jpg)

We invite citizens to participate in early detection through an app that allows:
*	Receive reports and view fires
*	Have information about active fires in your area
*	Obtain safe routes away from the fire
*	Gamification in the fire identification. The user will be shown images of possible fires that the decision model is not able to evaluate with sufficient certainty. The user will decide if it corresponds to a real threat or not. The correct decisions of the user will be rewarded with points in a ranking, in which you will be able to ascend from category.
 
### Landing Page (Web)

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/images/Web%20mockup.png)
 
There is also a public website where you can download the application and find useful information. Please visit: https://gohubvlc.github.io/sofia-landing-page/dist/index.html

### Source code

The source code are stored under a Gihub account. It contains source code for the iOS application, Sofia server, Augmented Reality APP for Android and all graphic files, documents and prototypes. The code are under GPL license and could be used for any purpose.

https://github.com/gohubvlc  

- Project & Documentation: https://github.com/gohubvlc/sofia-project
- APP: https://github.com/gohubvlc/sofia-app
- Landing Page: https://github.com/gohubvlc/sofia-landing-page
- Augmented Reality POC: https://github.com/gohubvlc/sofia-project/tree/master/Augmented%20Reality


## 4. DETAILS

### Fire Risk Model (FRM)

We estimate through the model explained in paper [1] the daily values of the fire risk rating using satellite products:
*	Daily surface temperature at 1km (i.e, MOD11A1) spatial resolution
*	Daily precipitable water (i.e, MOD05L2) at 1km spatial resolution
*	8-day composite of surface reflectance (i.e, MOD09A1) at 500m spatial resolution
*	Annual land cover map (i.e, MCD12Q1) at 500m spatial resolution
*	Daily aerosol optical depth model (i.e, MCD19A2) at 1km spatial resolution
*	Monthly burned-area (i.e, MCD45A1) at 500 m [\*]
Data is downloaded daily from https://ladsweb.modaps.eosdis.nasa.gov and https://search.earthdata.nasa.gov [*]

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/diagrams/SoFiaModel.jpg)

More information in the following [document](https://github.com/gohubvlc/sofia-project/blob/master/docs/SofiaModel.pdf).

### App UX flow
We show a flowchart of the APP:
 
![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/diagrams/UserFlowchart.png)
 
### Gamification in the fire identification and Social Network

Below is a scheme of how the game works and how it integrates with the AI:

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/diagrams/Gamification.jpg)

This is the ranking of users competing globally in three different categories

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/images/GamificationRanking.jpg)
 
More information in the following [document](https://github.com/gohubvlc/sofia-project/blob/master/docs/SOFIA%20Social%20Network.pdf).

### Escape and evacuation routes
Sofia APP proposes safe evacuation routes based on the identification of risk zones using Fire Risk Model information.

![N|Solid](https://github.com/gohubvlc/sofia-project/blob/master/diagrams/EscapeRoutes.jpg)

For more information see the following [document](https://github.com/gohubvlc/sofia-project/blob/master/docs/Escape%20routes.pdf).

### Social Media Scraping

A social media scraper refers to an automatic web scraping tool that extracts data from social media channels, which not only include social networking sites, such as Facebook, Twitter, Instagram, LinkedIn, etc., but also include blogs, wikis, and news sites. All of these portals share something in common: they are all yielding user-generated content in the form of unstructured data that is accessible only through the web.

For more information see the following [public article](https://www.researchgate.net/publication/286928406_Towards_an_algorithm_for_efficient_use_of_social_network_resources_by_using_Web_scraping_techniques).

## 5. OTHER SOURCES OF INFORMATION INTEGRATED IN THE PROJECT

* Population Density  
Annual population density data at approximately 1 km resolution were obtained from the Landscan global population database [3]. Data is downloaded daily from: https://landscan.ornl.gov/

* Visual Smoke Plume Detection  
Aerosol optical depth (AOD) using GOES-East and GOES-West with 30 min temporal resolution [4]. Data is downloaded from: https://www.ospo.noaa.gov/Products/atmosphere/aerosol.html

* Active Fires and Never Burnes Places  
Near real-time fire products are generated within approximately 3 hours from both the Moderate Resolution Imaging Spectroradiometer (MODIS) and the Visible Infrared Imaging Radiometer Suite (VIIRS). Data is downloaded from: https://firms.modaps.eosdis.nasa.gov/

* Burned Area Product (MCD45A1)  
Monthly gridded 500 meter product, which contains burning and quality assurance information. Data is downloaded from: https://firms.modaps.eosdis.nasa.gov/


## 6. CONCLUSION / FUTURE

We think that the real implementation of this project is viable given that it is based on tools that have widely proven their operation in similar fields.

The project would greatly benefit the health of the planet, and of all the living beings that inhabit it. In addition, we would reduce the cost of extinguishing fires, being able to allocate that money to improve even more prevention systems such as the project itself.

One way to improve predictions would be to differentiate between different sources of fire so that both users and fire detection algorithms learn to differentiate between smoke from forest fires and other types of fires. This, in addition, would contribute to improving the knowledge of the people about the behavior of the fire, improving their level of awareness with the problem.

As a result of studying this challenge in depth, we have many ideas that could complete the project, and surely the community could contribute.

The project can be extrapolated to all types of disasters, since the philosophy is the same: to use humans as active or passive "sensors" as a source of global information.

A crowfounding campaign could be created to materialize the project at a global level with crowsourcing code to involve as many people as possible from all countries, helping to obtain approaches from all parts of the planet.


## 7. TEAM

- Roberto Tórtola Contreras (Project analyst) - https://www.linkedin.com/in/roberto-tortola/
- David Pastor Calle  (Data scientist) - https://www.linkedin.com/in/david-pastor-calle/
- Lucía Martínez Fuertes  (Creative manager) - https://www.linkedin.com/in/lucía-martínez-fuertes-4767a666/
- José Medrano (Software Enginner) - https://www.linkedin.com/in/josemedranojimenez/
- José Luis González Jiménez  (UX + UI + FrontEnd designer) - https://www.linkedin.com/in/joseluisgj/
- Javier Cabañero Cabezuelo  (Augmented reality expert) - https://www.linkedin.com/in/javiercabezuelo/
- Jordi Oliver (Social media manager) - https://www.linkedin.com/in/oliverjordi/
- Sol Represa (Environment remote sensing specialist) - https://www.linkedin.com/in/solrepresa/


## 8. THANKS

- Anibal Navalón Torró (Surveillance of the forest fire prevention unit of the 'Comuniad Valenciana', Spain)
- Jonathan Knowles (Voice dubbing for the presentation video)


## REFERENCES

* [1] Chowdhury, E. H., & Hassan, Q. K. (2015). Development of a new daily-scale forest fire danger forecasting system using remote sensing data. Remote Sensing, 7(3), 2431-2448.
* [2] Abdollahi, M., Islam, T., Gupta, A., & Hassan, Q. (2018). An Advanced Forest Fire Danger Forecasting System: Integration of Remote Sensing and Historical Sources of Ignition Data. Remote Sensing, 10(6), 923.
* [3] Thakur, G., Sims, K., Mao, H., Piburn, J., Sparks, K., Urban, M., et al. (2018). Utilizing Geo-located Sensors and Social Media for Studying Population Dynamics and Land Classification. In Human Dynamics Research in Smart and Connected Communities (pp. 13-40). Springer, Cham.
* [4] Sowden, M., Mueller, U., & Blake, D. (2018). Review of surface particulate monitoring of dust events using geostationary satellite remote sensing. Atmospheric Environment.
* [5] Chowdhury, E. H., & Hassan, Q. K. (2015). Operational perspective of remote sensing-based forest fire danger forecasting systems. ISPRS Journal of Photogrammetry and Remote Sensing, 104, 224-236.
