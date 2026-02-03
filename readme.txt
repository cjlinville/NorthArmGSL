Great Salt Lake North Arm Decline Analysis

This script analyzes the rate of water loss of the North Arm of the Great Salt Lake between Jan 1st, 2013 to December 16, 2016.
During this time, the north arm was isolated from the south arm due to culvert construction on the causeway that separates the two arms.
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