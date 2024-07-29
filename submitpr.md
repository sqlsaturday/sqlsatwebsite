---
layout: page
title: Submitting a PR for an Event
permalink: /pullrequest/
---

This page is designed to help you understand the GitHub repo and how to manage the settings and display of your event on the site.

**Note:** If you have not worked with GitHub and submitting Pull Requests from a fork, Rob Sewell has a great post to help you: [How to fork a GitHub repository and contribute to an open source project](https://blog.robsewell.com/blog/how-to-fork-a-github-repository-and-contribute-to-an-open-source-project/) [[Mirror Link](https://web.archive.org/web/20240412114152/https://blog.robsewell.com/blog/how-to-fork-a-github-repository-and-contribute-to-an-open-source-project/)]

If you have issues with these instructions, please feel free to contact the webmaster for this domain.

If there are settings you'd like to see added to your website, please also contact us.

## Event Page Structure

A new event consists of two items:
- A markdown file with the event metadata
- A data file in YAML format.

Each of these is fairly simple to work with, but an understanding of markdown and YAML is needed. Each file is discussed below.

### Event Markdown File

The event markdown file is stored in the _posts folder and should have this structure for the name.

~yyyy-mm-dd-sqlsaturdaynnnn.markdown

The values to set are:
- yyyy: the year of the event
- mm: the month number of the event (2 digits)
- dd: the day of the event. If you span multiple days, choose the first day. I would ignore pre-con days, but that is up to you.
- nnnn: The four digit event number. We restarted with 1020, and you can choose the next number not taken in the _posts folder.

As an example, the 2021 data.SQL.Saturday LA event is: 2021-06-12-sqlsaturday1020.markdown

The contents of this file are the metadata for the event. A sample is shown below, with each item described.

~~~~
---
layout: event
title: "SQL Saturday Los Angeles June 2021"
subtitle: ""
tags: [LosAngeles, California, USA, virtual, 2021]
thumb: /assets/img/logos/Just_icon_Color_small.png
comments: false
data: SQLSat1020
---
~~~~

The layout is required as the type of page we are displaying.

The title is the title of your event. We would like to see the title be SQL Saturday <location> <month/season> <year> to differentiate one event from another if there are multiple ones in a location in a year.

You can add a subtitle if you wish. This will be displayed below the title. This could be the tagline, motto, or other descriptive item for your event.

For tags, we have started to add the city, state, country, type of event, and year for categorization by users of the site. Feel free to add others.

If you have a logo, add a path to this file. Upload logos as a part of your PR in /assets/img/logos. This should be a small, 100x100 or less image.

Leave comments set to false.

The data file is listed here. Use SQLSatnnnn as the file, which is described below.

### Event Data File

Most of the settings for your event are placed in a data file in the /_data/events folder. In here, create a YAML file as SQLSatnnnn.yml, where nnnn is the number of your event.

YAML files are key value files, and follow a structure that requires whitespace for formatting. Each of the keys is described below, some of which are subkeys. I tend to use Visual Studio Code and the [YAML extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) to help ensure I comply with the standard.

Each of the values for these keys controls the display of your event page, so adding these often changes the way the page appears.

- **Name**: This is the name of the event. This is displayed at the top of your page.
- **logo**: If you have an event logo, add the path to the logo file. I would keep this below 800x600. Use quotes for the path. This appears below the title. If there is no logo, you can leave this value blank.
- **logocredit**: This is a credit line for artists to display below the logo. You can leave this blank and nothing is displayed.
- **date**: the date of your event, in timezone format. yyyy-mm-dd hh:mm:ss -tztz. This is important for those that might run virtual events, as you want the time zone to appear.
- **virtual**: set to true if you are running a virtual event, false otherwise. This is displayed below the description after "This event is:". The next two settings relate to this.
-  **physical**: set to true if the event is live with attendees coming in person. Displayed as the virtual key.
- **hybrid**: set to true if this is a hybrid event. Displayed as the virtual key above.
- **dataprivacy**: leave blank to use the default SQL Saturday data privacy. Add in inline HTML for your specific policy.
- **description**: This is the description that you want to display below your title and logo. If this is a multi-line value, use a pipe on the first line of the key and start the description below. Indent each line with 4 spaces.
- **officialwebsite**: If you have your own website, you can enter a URL here and the page will show: "official website" and then this link. Leave blank if you do not have your own website/page.
- **eventlocation**: text descrption of the location for your event. Leave blank for virtual. If multiline, format as html. Indent each line with 4 spaces.
- **registrationurl**: The URL for your attendee registration. For example, the LA event uses Eventbrite and had this as the value - "https://www.eventbrite.com/e/virtual-2021-datasqlsaturdayla-tickets-136013374665". This is used as the target behind the "Register Now" button.
- **capacity**: If you have a capacity limit, you can enter a value here. If this is not blank, the text "The capacity for this event is " is printed with this value. This can be numerical or text.
- **precons** - Set to true if running precons. This will print the precons menu link and show the precons subsection. Fill out *precondetail* with the HTML for precons.
- **usingrooms** - If true, the Rooms section is shown.
- **googlemapurl**: If you have a google maps URL for your event location, this will pull in the map in an iframe and print it on the page. Use the share link, and the embed. Get the URL and put it in this key. **This is not the URL in the Browser**
- **scheduleurl**: If your schedule is set, this is the place for a sessionize schedule URL. This should look something like "scheduleurl: https://sessionize.com/api/v2/a3ebxb7v/view/GridSmart". If you have no schedule set, leave this blank.
- **scheduletimezone**: Text for your time zone. We print this below the "Schedule" section on your page, above the schedule itself.
- **eventcountdown**: set to true if you have a value for the countdownscript value below.
- **countdownscript**: this value has been tested with logwork.com. If you set up a script with them, include your script source in quotes here. This would be the "script src=" with the html brackets around it.
- **speakertext**: This is text you'd like to use below the "Speakers" section on your page.
- **speakerlisturl**: If you wish to link to a list of speakers, enter a value here. Your sessionize page will contain a list of speakers and sessions submitted.
- **callforspeakersurl**: This is the link for your call for speakers provider. Sessionize.com seems to be the preferred provider for everyone these days. This is only displayed if the callforspeakers key is set to true.
- **callforspeakers**: true for open calls, false otherwise.
- **callforspeakersenddate**: the date on which your call for speakers closes. This is printed if the callforspeakers is set to true.
- **organizers**: This key is blank, but it has subkeys. Each of these subkeys is described, and if you have multiple groups of subjects, each needs a hypen at the beginning and we will print each group of these at the bottom of your event page under the "Contact the Organizers" section. This can be a group instead of individuals.
  - **name**: The name of the organizer as you want it printed.
  - **twitter**: a twitter handle for the organizer, minus the @. leave blank if you have none. This is hot linked to Twitter. 
  - **email**: An email address for contacting this organizer.
  - **url**: If this organizer or group has a website, add here. Leave blank if not needed. Include the http://.
- **volunteers**: Another key with subkeys. Leave blank.
  - **description**: text you'd like to have printed under the "Volunteers" section on your page.
  - **volunteerurl**: a signup form URL to link on the page. If blank, nothing is printed.
- **social**: another key with subkeys. Leave blank.
  - **twitter**: if you have a twitter account for your event, add here. This is used as the target of a twitter icon below the table of contents. If blank, no twitter icon is shown.
  - **youtube**: if you have a youtube channel for your event, add here. This is just the name of the channel, not a URL. This is used as the target of an  icon below the table of contents. If blank, no icon is shown.
  - **linkedin**: if you have a LinkedIn URL for your event, add here. This is the full URL. This is used as the target of an icon below the table of contents. If blank, no icon is shown.
  - **instagram**: if you have a instagram account for your event, add here. This is the handle, not the full URL. This is used as the target of an icon below the table of contents. If blank, no icon is shown.
  - **tiktok**: if you have a TikTok account for your event, add here. This is the handle, not the full URL. This is used as the target of an icon below the table of contents. If blank, no icon is shown.
  - **pinterest**: if you have a Pinterest account for your event, add here. This is the handle, not the full URL. This is used as the target of an icon below the table of contents. If blank, no icon is shown.
- **sponsorcontacturl**: A URL if you have a place for sponsors to sign up or contact. If you wish to set up sponsorship plans, you can set up a second EventBrite with different types of tickets for sponsors to "purchase" and fund your event.
- **sponsors**: another top key with subkeys. Leave blank. If you have multiple sponsors, repeat this set of keys, starting the new group with a hypen in front of the first key.
  - **link**: the url to which you redirect clicks on the sponsor logo.
  - **image**: the path to the logo. /assets/img/logos is where you submit your logos in the repo.
- **join**: This is a top level key. Leave blank.
  - **description**: text you want printed below the "Rooms" section on the page.
  - **rooms**: This is a subkey. Leave blank. 
    - **name**: If you have rooms for broadcast, you can add a name here. This set of keys can be repeated as needed. You do not need a URL to add rooms.
    - **url**: the URL to link the room button to. Blank before you have URLs assigned.

