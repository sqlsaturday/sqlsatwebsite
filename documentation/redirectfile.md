---
layout: page
title: Redirect File
permalink: /documentation/redirect/
---
This file is created to provide a shortcode redirect for an event

**For a new event**: Create or edit this file once the event has gone live.

## File Details

The redirect file provides a short URL for an event. This is a URL such as [https://sqlsaturday.com/jax](https://sqlsaturday.com/jax), which redirects to the current Jacksonville event. Each year, this file is edited to reflect the current event.

These files are in the root of the repository, and are .html files. Examples of these files are:
- jax.html - Jacksonville event
- nyc.html - New York City event
- lima.html - Limi, Peru event

The file has a header similar to posts, with three hyphens on the first and last lines of the file. Between these markers, there are two keys with two values in YAML format. These are:
- redirect - the URL to which this shortcut will redirect. Edit this to point to the current event for any location.
- layout - This is always "redirect"

