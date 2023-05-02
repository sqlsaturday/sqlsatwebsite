---
layout: page
title: Event Post File
permalink: /documentation/eventpost/
---
This file is created to provide the landing page for an event.

**For a new event**: Create this file first
## File Details

The event post file is the blog post in Jekyll that describes the event and determines the date order in which is it shown. Each of these files is stored in the _posts folder with the following format: yyyy-mm-dd-SQLSat-nnnn.markdown. The values for each part of this name are:
- yyyy - The year in 4 digit format, i.e. 2023
- mm - The month in two digit format, i.e. 01 or 12
- dd - The day in two digit format, i.e. 02 or 22
- nnnn - a sequential number indicating the next numerical event. This value is assigned by SQL Saturday. If you do not know the next event, you can look in _posts and choose the next one for your PR or contact the webmaster.

The rest of the values should be included as it. A few examples of events:
- 2007-11-10-SQLSat-0001.markdown - The original Orlando SQL Saturday on Nov 10, 2007
- 2020-03-07-SQLSat-0929.markdown - The Baton Rouge BI Event just before the pandemic
- 2021-06-12-sqlsaturday1020.markdown - The first SQL Saturday under the non profit charity after the PASS organization declared bankruptcy

The structure of this file is a YAML structure that is contained within the Jekyll header structure. The file should have three (3) hypens on the first line and three (3) hypens on the last line. In between these tow lines we need a YAML document of key/value pairs.

The following keys are in use:
- [layout](#layout)
- [title](#title)
- [subtitle](#subtitle)
- [tags](#tags)
- [thumb](#thumb)
- [comments](#comments)
- [data](#data)
- [postponed](#postponed)
- [testevent](#testevent)

Each key is described below.

### <a name="layout"></a>Layout
This value is required and should always be "event". This is the type of file to be rendered under Jekyll, and matches the type of layout in use under the _layouts folder.

### <a name="title"></a>Title
This value is required and should be the title of the event. The convention is "SQL Saturday city yyyy (#nnnn)" where yyyy is the year and nnnn is the event number from the filename. The city is the city in which the event is taking place. However, this can be overridden. As a few examples, these are names used for titles:
- SQL Saturday Jacksonville 2023 (#1041)
- SQL Saturday New York City 2023 (#1048)
- Ohio North SQL Saturday 2023 (#1055)
- 2023 data.SQL.Saturday.L.A (#1049)

We are not too concerned with naming and will be flexible with event organizers.

### <a name="subtitle"></a>subtitle
This key is not used and is optional

### <a name="tags"></a>tags
This key is a JSON array used to apply tags to this event. These tags are surfaced on the [tags](https://sqlsaturday.com/tags/) page. Feel free to add as many as you like.

The typical tags that we use are the following:
- city - Use the city or cities nearby. For example, the Ohio North 2023 event has both Cleveland and Akron tags as the past events were in Cleveland, but the event this time is actually in Akron.
- state/county/region - Use local names
- country - Use the country name or USA
- year (4 digit format)
- physical/virtual/hybrid (choose one)
- continent - one of (North America, South America, Asia, Europe, Africa, Oceana, Antarctica)
- area of focus - such as BI, Azure, cloud, etc.

### <a name="thumb"></a>thumb
This value is the thumbnail image used on the front page. This should be "/assets/img/logos/Just_icon_Color_small.png", but can be overridden if desired.

### <a name="comments"></a>comments
This key should always be false. We do not accept comments on events.

### <a name="data"></a>data
This key contains the numerical value for the event data file that contains configuration for this event. The data files are located in the _data/events folder. Each is named SQLSatnnnn.yml. The nnnn is the number in the filename of this file, and is the value used here. The value here should match the data file name without the extension.

For event 1023, this value is SQLSat1023.

### <a name="postponed"></a>#postponed
This value is a flag if the event has been postponed and there is no new date. Use a 1 here if the event is postponed. A zero or no key means the event is not postponed.
### <a name="testevent"></a>testevent)
This value is a flag if the event has been postponed and there is no new date. Use a 1 here if the event is postponed. A zero or no key means the event is not postponed.

