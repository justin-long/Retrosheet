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

If this is not the case, then all the .bat files will need modified.

## General Steps

### Preliminary Steps
* Download entire repository, and place directly in C:\ directory
* Download all the required programs
* Update aria2c.exe path in data\zipped\get_zip_files.bat (May not be neccessary)
* Update 7-zip.exe path in data\zipped\get_zip_files.bat (May not be neccessary)

### Downloading the Data
* Run get_zip_files.bat in data\zipped folder (Will download all retrosheet files and unzip them)
* Run the three .bat files in the data\unzipped folder (Will use Chadwick programs to parse the data)

### Loading the Data
* Open MySQL and create a new schema titled retrosheet (Create empty database)
* Run the retrosheet table schema SQL script (Create tables for database)
* Run the three SQL programs in the loaders folder (Load the data into the tables)
* Run the partition SQL script (Partition the data for faster querying)
* Check the events, games, subs tables. If not empty, then drop the tables with the _bck prefix




