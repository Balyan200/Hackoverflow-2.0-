# FIND my Activity

Find my Activity is a Machine Learning model that flags(predict) the inactivity of a vessel's AIS in Baltic sea area. 
## Problem Statement
This project deals with the below problem statement of Hackerflow2.0 (https://github.com/hackoverflow2/Hackoverflow-2.0/tree/main/Blue%20Economy) :
###Flagging of (AIS) INactivity Data (FIND) - (Blue Economy)
AIS is a useful system that helps to avoid ship collisions and allows managers of fleet management, especially for emergencies e.g. adverse sea conditions. Vessels keep the AIS beacons on in order to stay safe. However, sometimes the vessels do not transmit. The reasons for this may be unknown. As much as the AIS activity data are important, the inactivity data can also be put to use to understand the possible reasons behind such behavior and if needed, respond in the appropriate manner. The interactive tool should be able to categorize the AIS inactivity episodes for a single vessel or multiple vessels in a selected region. Further, the data may be classified based on the ship behavior prior to the inactivity, as well as based on various inactivity parameters such as location, time and duration of inactivity.
## Description and features
AIS (Automatic Identification System) is a program fitted into marine vessels that transmits vessesl's locometric data as vessel identification(mmsi), position(latitude and longitude), speed and course to a shore station and other vessels. The actual reason behind 
We collected the data from  IEEE dataport (Ville Hakola, February 28, 2020, "Vessel tracking (AIS), vessel metadata and dirway datasets", IEEE Dataport, doi: https://dx.doi.org/10.21227/j3b5-es69.) The training set which we worked upon ranged from AIS collected features as Timestamp, lat,lon, speed and many more attributes of around 1833 vessels and a record of 14185046. We used a subset of this dataset with a record of 90 vessels.
The data was not prelabelled for inactivity, therefore we considered the timestamp duration as our measure for inactivity. According to vessels' mmsi categorisation, the records where there was extensive variation in timestamps, the corresponding location was tagged as Inactivity point. 
Furthermore, density of occurence of inactivity of different vessels over months of the year 2017 and 2018 is analysed and flagged as:
1) 0: Unknown :- the reason is unknown( maybe it was intentional or some error) 
2) 1: Geographic reason :- Many vessels were found to be inactive in the area at a time which indicates geographical tensions or may be saturation of system due to high vessel density
3) 2: Poor transmission signal

After manual labelling and preprocessing, Random forest, logistic regression and linear regression algorithms are used for prediction with 100% accuray of Random forest model.
