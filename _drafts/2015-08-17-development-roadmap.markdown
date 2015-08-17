---
layout: post
status: publish
published: true
title: Development Roadmap
date: '2015-08-17 12:00:00 +0300'
author: Yuval Adam
---

In last week's blog post we discussed [5 things you can do with Synereo, right now](http://blog.synereo.com/2015/08/12/top-5-things-you-can-do-with-synereo-now/). Today, we'll try to give some more insight into our current development efforts and roadmap ahead. Developers and users who are following our weekly hangouts closely (pro tip: [here's the next one](https://plus.google.com/u/0/events/c8kibm683jmmadlvunh83bf34tk)) have good insight into our efforts, but we understand this knowledge doesn't percolate to the rest of the community, unless we put it up nicely in prose :)

The first of our development efforts is to package the existing bits into a form which developers can easily start hacking on. To that end, we're going with Docker to [containerize all the Synereo code](https://github.com/synereo/dockerfiles) and have it running happily across various environments. Initially this will enable developers to run the same tests we're running as we ramp up development, and later on we'll be able to build on top of that foundation to allow end-users a single click deployment of a complete Synereo node.

Secondly, we're moving [all of the front-end code to a new architecture](https://github.com/synereo/nuui) that's based on Scala.js and Spray.... (expand)

Once those two tracks near completion, we'll be integrating them together to have a complete Synereo node running on Docker, hopefully with a nice UI. (expand)

Discuss other avenues of expansion? Ethereum? Music?
