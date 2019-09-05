---
author: Daniel Noe
date: "2019-08-12T15:04:10.000Z"
description: Writing a Blog is Fun
section: Metadata
tags:
  - metadata
thumbnail: daniel-noe.jpg
title: My Experience With Parsely
type: NewsArticle
url: https://parsely-hw-daniel.netlify.com/daniels-blog/
---

Things started out pretty smoothly. 

I followed the first five steps with virtually no issues except for two minor things. The first holdup was when I pasted "gatsby develop" into terminal and it didn't work because I was missing some dependencies. The second setback happened when I tried to deploy the site using Netlify and it failed. I spent about 30 minutes trying to figure out what happened before I decided to simply "retry deploy" and for some reason it worked.

Then things got a bit more interesting. I started going through the self-service installation of Parsely and I realized that my unfamiliarity with Gatsby was a problem because I couldn't figure out where to put the tracking code (<script id="parsely-cfg" src="//cdn.parsely.com/keys/parsely-hw-daniel.netlify.com/p.js"></script>). I was looking for an index.html file but for some reason missed it. That's when I remembered the instructions Annelise has linked and followed that instead (https://www.gatsbyjs.org/packages/gatsby-plugin-parsely-analytics/). Pretty easy but it seems steps 6 and 7 of the ReadMe might have some overlap since in theory one wouldn't need step 7 if one were able to follow the tracking code installation instructions via the self-service integration process.

I finally open the dashboard and much to my lament there is literally no metadata showing:

![No Metadata Showing](./No Metadata Showing.png)

The first thing I tried doing was going to the gatsby-config.js file and changing the Gatsby/Parsely plugin from "False" to "True." That didn't seem to work so I evenutally changed it back. 

I spent a lot of time reading the integration documentation and everything I could about metadata and JSON-LD tags here: https://www.parse.ly/help/integration/basic/. I also got a hint from Annelise and checked out the metadata of some live Parsely blogs. After searching my text editor for "application/ld+json" (found in the blog-post.js file), I went and found the index.md file for each blog and rearranged in specific order all the metadata and started filling in the empty fields and also changed all the blogs to @type = NewsArticle. I made myself a litte cheat sheet based off the information in blog-post.js (below) to help me keep track and make sure I wasn't missing anything:
@context = schema.org
@type = type
Headline = title
Creator = author
URL = N/A
ThumbnailURL = thumbnail
DatePublished = date
ArticleSection = section
Keywords = tags

Ever since then the strangest thing has been happening. Only one of the blog posts has been showing up in the Parsely dashboard for me: https://parsely-hw-daniel.netlify.com/meta-metadata/. None of the others appear to even be getting pageviews as far as Parsely is concerned.

I have tried tackling this in a number of ways. I tried using the troubleshooting tool on the website






Parse.ly uses [metadata](https://www.parse.ly/help/integration/jsonld/) all the time, and [our customers use metadata](https://blog.parse.ly/post/8659/the-magic-of-metadata/) to drive content insights.



Credit [XKCD](https://xkcd.com/)
