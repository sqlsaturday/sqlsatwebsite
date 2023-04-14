# SQL Saturday Website

This is the main repository for the SQLSaturday.com website. All code in the folders is used to generate the SQLSaturday.com website. This is hosted and published as a GitJHub pages site. The generation of the site is through GiHub actions and is based on the Jekyll framework.

## Adding a new event
Two main things and one optional one.

First, add a new YAML file with the next event number in the _data/events folder. You can copy an existing one and change the various values.

Second, add a new post in the _posts folder, using the naming format of the existing posts. The date of the event is the first part of the filename, and the new number of the YAML file goes at the end.

Optionally, you can update or add a redirect .html file in the root. Each redirect file is unique to the event location.
