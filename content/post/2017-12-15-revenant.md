---
title: "Revenant"
date: 2017-12-15T23:28:57Z
tags: ['Servers','Tech','Heroku']
---

**It's over a year** since I wrote anything here, and 'here' has moved anyway. I was terribly proud when I moved over to
Digital Ocean, having never done much in the way of server admin before, and bothered to set up Nginx, Postfix, Dovecot,
Nagios, Caddy... In hindsight, it was sort of an achievement, but it was also a colossal waste of effort in many ways.

In the last year of being employed to do that sort of thing as my day job, I've realised just how much value there is in
getting *someone else* to do these things for you. Especially the maintenance. My email and calendar are now through
GSuite, rather than maintaining my own mail and calDAV servers. This site is on Heroku; someone else deals with the
infrastructure, I just `git push` and let it get on with being a website. Even the SSL is straightforward now that Heroku
supports on-demand SSL certificate creation with LetsEncrypt, although that does require using the paid tier which is
perhaps a touch of overkill for a personal blog. We'll see how things pan out; it's probably worth it. I feel quite
strongly that nobody should ever serve a site without SSL these days, even if it's trivial content.

It's always worth rolling one's own software stack as a learning experience, but over the last sixty years or so there
have been a tremendous number of very smart and motivated human beings who have dedicated their careers to building
tools and platforms. The Google codebase would take thousands of years to rebuild, if it were to be attempted by just
one motivated individual; not taking advantage of that investment would be foolish, even if precautions are necessary to
avoid having one's data stolen and used for advertising.

As a first post back, it would probably be a good idea to have some sort of update. Personal side: I've now held down a 'real job'
for over a year, am in the process of buying a flat, and earn enough not to panic about money regularly. I've continued one
relationship, and started/enjoyed/amicably terminated another.

Professional side: I've upskilled massively. Fourteen months ago, I knew a bit of Ruby, a bit of Python, a little Go,
and enough sysadmin stuff to be dangerous. Now I'm a primary maintainer of a gigantic legacy RoR application,
the infrastructure and build pipeline associated with it, and the networking on which it depends.

I've ported said application from a single VPS (including the database...) to an active-active cluster of GCE instances,
a dedicated MySQL instance, and a fully load balanced network - and an identical staging environment. In the process
I've reduced the release cycle of the application from two months to two weeks, and dramatically increased the maximum
load tolerance. Nothing's perfect - this solution is slightly more expensive than the previous situation, but it's much
better for business continuity and will hopefully allow me to push for a much faster cycle of shorter releases.

I'm learning Rust as a second systems programming language, and enjoying it; it's less fluid than Go, and the compile times
are comparatively awfully slow (although that is being worked on), but the actual experience of working in it is much
more pleasant. With Go I felt that the language didn't allow me to do certain things. With Rust, it's quite clearly
assisting me in not shooting my foot off. The compiler messages are polite and explicit, with the result that while Rust
rarely compiles first time, once it does compile it generally does exactly what it was supposed to in the first place.

I've decided to resurrect this place, largely because I need the writing practice. I'll work out what I actually want to
say as I go along, I expect. There will probably be food involved.
