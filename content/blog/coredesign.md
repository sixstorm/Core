---
title: "Core Design"
description: "Why Does This Look So Bland?"
date: 12/09/2021 12:58:00 -0600 CST
tags: ['core','blog','tech']
---

As promised, let's quickly talk about the design behind Core and the "why" behind it.

# Simple

As I've mentioned before, I wanted Core to be as simple as possible.  At the date of this writing, I have 1 image on the entire site under the [Doom Eternal](https://teamtuck.xyz/tech/DoomEternalUNRun) post, and even that image is not properly optimized . . . I should get on that.  Having a static site page really helps in taking simple content, generating basic HTML pages so that it's easy for the reader/client to download them.  Usually most websites don't do this and think that "flash" is the key to having a beautiful and successful site.  While I'm not going for either of those things, I appreciate what some web designers do but it's not what I'm about.  There's no show here.  Just me and my content.

# Colors

This was a hard choice to make, even harder to figure out which colors went where.  Every time that I dabble with web design/site creation, picking a color scheme is the hardest part.  It's super easy to find a site to generate a color palette, but it's up to you to assign colors to specific elements.  What color should the background be?  What color should the text be?  Headers?  Table headers and table items?  The list goes on and on.  

I chose a palette that included two of my favorite colors:  blue and gray.  The last version of Core included my favorite shade of gray, which is Gunmetal Gray.  I thought it would be better to try something different, pick something a little more colorful.  When I found this palette, I thought it would be some simple and easy on the eyes, while having a little style at the same time.  Most web sites that are "minimal" stick to basic black and white, but I'm not that basic.

# Bulma

I've never dealt with a CSS "helper" like Tailwind, SASS or Bulma because I've always been unaware, typing out and creating custom CSS for myself.  My friend [Urreta](https://urreta.io/) recommended Bulma because it was simple to use and customize, making the site "mobile first".  Instead of creating all kinds of classes yourself, you can use the built in classes to automatically position content, center, define columns, etc.  And yes, this is a much easier option than custom CSS!  The site I had envisioned didn't need custom CSS or animations.

It took me a few days to get used to how Bulma works and how to play by its rules, but once it clicked, it was off to the races.  I originally wanted all of the content centered but that changed quickly; I decided to keep things left-aligned as it just looked better that way.

# Future Plans
Honestly I'm going to keep the color scheme and design as it stands for a while.  I will probably make some change to the color palette next Spring if I feel like it.  Also, the site will grow and expand naturally, as it should.  There's no telling what it will look like in a month or year from now, so we will just make changes as needed.

If you look at Core on a mobile device, there are design elements that desperatly need worked on; this will most likely be the next thing on my to do list.

In the next segment, I'll discuss how I learned Git to manage this site as well as how I host it.
