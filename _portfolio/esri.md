---
title: "Esri Products"
excerpt: "A short list of my background with ArcGIS software development"
header:
  <!-- image: foo-bar-identity.jpg -->
  teaser: esri.png
sidebar:
  - title: "Role"
    image: esri.png
    image_alt: "ESRI logo"
    text: ".NET Desktop Developer, C# Programmer, DBMS administration"
  - title: "Responsibilities"
    text: "Develope and support a working and bug-free software package for the end-users"
gallery:
  - URL: foo-bar-identity.jpg
    image_path: foo-bar-identity-th.jpg
---
{% include toc icon="" title="Table of Contents" %}

I have started working seriously with ESRI products since I graduated from university in 2010. I have been part of many national GIS projects in both private and governmental sectors although my focus of contributions has been on utility (electricity, gas and etc) and municipality GIS application. Here are an excerpt of my projects:

## ArcObjects
I love ArcObjects due to its matureness. There is almost no GIS library that is as complete as ArcObjects. ArcObjects is robust, stable and covers almost any GIS task from trivial spatial query processing to advanced network analysis. Many people believe learning ArcObjects has a steep learning curve and I admit they are right. However, I have been involved in ArcObjects development since 2010 and consider myself as a pro. As of today, I am able to solve even the [toughest GIS problems](http://gis.stackexchange.com/questions/165077/how-to-add-a-new-parcel-inside-parcel-fabric-from-existing-parcel-features-arco/166021#166021) with ArcObjects in a timely manner.

### Digsilent/CYME converter Addin
Electricity network is one of the most complex types of geometric networks that can be easily managed within the context of GIS. Feeders, overhead/underground lines, substations, switches, busbars, and transformers are the prevalent electricity network features. GIS is the most appropriate tool to store, manage and analyze static electrical assets. However to analyze dynamism of electric network one may need other specialized software packages for example [Digsilent](www.digsilent.de) or [Cyme](http://www.cyme.com/software/cymdist). 
I developed this ArcGIS Addin to trace an electric network and then export spatial features to an intermediate format (`.dgs` for Digsilent and `.txt` for CYME). The generated textual file can be imported to the corresponding software to carry out further analysis i.e. short circuit analysis.

### Network Tracer Tools
I have developed custom network tracers such as "Feeder Network Tracer" for electric and "Valve Isolation Tracer" for the gas network.

### SDE User Manager Application
Although it is feasible to manage users and define security levels for data sources with ArcGIS built-in Geoprocessing tools, it is not the most intuitive way to achieve these goals. SDE User Manager is a WinForm ArcEngine application to streamline user management workflows. It allows the system administrator to do the following tasks in a unified GUI:

- Create, edit and remove users and groups from Geodatabase 
- Define access levels (read, insert, delete and update) for the Geodatabase data sets
- Follows Esri best practice for user management e.g. assigning privileges to groups/roles instead of user

![SdeUserManager](sde-usr-mngr.jpg)

### Basemap Manager Addin
Google maps are appealing and everybody loves them. This ArcGIS Addin utilizes Google maps API and adds the following functionalities to ArcMap:

- Add Google maps and satellite imagery layers to ArcMap as a WMTS layer and supports tile caching. It can be used in online and offline mode
- Support for Google Geocoding API: Users can search places from within ArcMap
- Uses HTML5 Geolocation API to locate ArcMap user location on the map (this feature needs active Internet connection) 

![OnlineMaps](online-maps.jpg)

### Editor/Geodatabase Extension
I have used "Editor Extension" to create editor construction tools to draw features in batch mode. For example in a gas utility network, the GIS data editor can draw a "service line" and "service point" simultaneously instead of drawing them one by one. Geodatabase extension is the best approach to feature's update/insert/delete event handling because they are application independent. I have used them with projects that the edits came from the web, mobile and enterprise users.

### SOE (Server Objects Extension)
Although an Arcpy script can be shared as a Geoprocessing tool and be used by ArcGIS Server, yet they are not very efficient; they have a large memory footprint. For fine grained and repeated work-flows, ESRI suggests Server Objects Extension (SOE). I have not been involved in many "ArcGIS Server" based projects but I have exposed some of my handy functions (e.g. network tracers) as RESTful web services through SOE to be called by 3rd party applications. In addition, piping a functionality through standard OGC web services allows ArcGIS web clients, such as javascript API, to consume them efficiently.

## ArcPy
I have written many Python (ArcPy) scripts to automate my workflows. Python is part of ArcGIS system and it is integrated with different sections of the software - ArcGIS system without python is not imaginable. An excerpt of my python scripts:

- Python script to automate map book production
- Script to convert data from Smallworld VDMS format to FileGeodatabase
- Read thousands of excel spreadsheets and import them into Geodatabase
- [Comtypes with Arcpy](http://gis.stackexchange.com/questions/178532/in-arcmap-use-python-to-disable-scale-map-elements-proportionally-to-changes-i) to access features of ArcObjects that are not exposed to Arcpy
- Toolboxes and tools to automate my daily GIS tasks

## ArcSDE
For customers that software price is a critical parameter I always suggest PostgreSql (PG) as the database back-end. PostgreSql is both free and powerful and ESRI supports it comprehensively. Although I still believe no database could beat Oracle in terms of performance and scalability. I have used PG in my projects with ESRI SDE  data type and functions which are independent of PostGIS. Furthermore, I always suggest ArcSDE direct-connect with the native DBMS client as per ESRI recommendation. In addition, I have utilized many of the enterprise level PostgreSql backup features in miscellaneous projects as follows:

- Hot backup
- Weekly base backup with daily incremental backup
- Script to auto-compress backup files
- Store backups on any device including external H.D.D, network share, Tape and etc
- Point in time recovery
- Remote backup
