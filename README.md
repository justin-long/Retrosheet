# Retrosheet
This repository contains the folder structure and programs needed to create and load a Retrosheet database into MySQL.

## Background information

This is an updated version of [these guides.](https://www.fangraphs.com/techgraphs/building-a-retrosheet-database-for-the-2016-season-part-1/)

I've modified the files to include games from 1921 - 2017.

I also changed the batch file to download the retrosheet files. Originally the downloads were done using wget, but there were issues with SSL authentication, so it now uses aria2.

## Prerequisites
* MySQL
* Aria2
* 7-Zip
* (Optional) Notepad++

## Program Modifications
This program assumes that these folders were copied directly into the C:\ directory, i.e. C:\Retrosheet\...

If this is not the case, then all the .bat files in the data\unzipped folder will need modified.
