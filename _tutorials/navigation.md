---
title: Navigation
author: tomjoht
date: 2017-01-24 15:38:17 -0800
---

If your Jekyll site has a lot of pages, you might want to create navigation for the pages. Instead of hard-coding navigation links, you can programmatically retrieve a list of pages to build the navigation for your site.


There are two primary ways of retrieving pages on a Jekyll site:

* **Retrieve pages listed in a YAML data source**. Store the page data in a YAML (or JSON or CSV) file in the `_data` folder, loop through the YAML properties, and insert the values into your theme.
* **Retrieve pages by looping through the page front matter**. Look through 
