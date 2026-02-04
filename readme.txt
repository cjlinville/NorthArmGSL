Great Salt Lake North Arm Decline Analysis

This Jupyter notebook analyzes water loss in the North Arm of the Great Salt Lake from January 1, 2013, to December 16, 2016.
During this time, construction on the culverts beneath the causeway isolated the North Arm from the South Arm, isolating the two basins.
Using daily lake stage observations, a stage–area–volume relationship, and two different modeling approaches, 
we can esimate the amount of time it would take for the north arm to fully dry up if these conditions became permanent.

Two approaches were taken in the jupyter notebook:

A linear volume trend (constant km³/year loss)
An area feedback model (constant net depth loss, shrinking area)


Overview
At a high level, the jupyter notebook does the following:

Reads daily USGS lake elevation data for the North Arm (USGS/Daily_Combined.csv)
Converts elevations to feet, then to NAVD88 vertical datum (what the stage area volume table is in)

Reads USGS stage-area-volume table for the North Arm to convert elevation to volume and area

Calculates daily change in lake volume

Fits a trend line to the change in lake volume to derive the average change in volume of the lake 

Two models:
1.) Linear extrapolation deriving the amount of time it would take for current volume to reach zero
2.) Extrapolate using change in area to inform estimated depth loss

Input data:
Daily_combined - daily average lake levels reported in meters, NGVD29

Great_Salt_Lake_2023_ElevAreaVolume_north_arm.csv - Stage-area-volume table that relates all three aspects.
This table encodes the hypsomtry of the lake. Values reported in NAVD88


Results:
The rate of water loss during the observation period was found to be -0.5519 km³ per year

The linear extrapolation produces a zero water timeline of about 7.3 years (see below).
Implementing the effect of surface area on the rate of volume loss produces an estimate of 13.9 years.

See the ModelOutputGraph.png in the repo for visual representation

Assumptions:
One major assumption is that the conditions during this time period are typical. 
There were a few months that had anormally high precipitation, so that is something to consider.

Another assumption is that if the north arm were to be cut off, it would experience similar conditions to what it did in 2013-2016.