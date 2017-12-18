---
title: "Deprecation"
date: 2017-12-18T13:14:37Z
tags: [tech]
---

At my current employer, the primary product is a massive Rails monolith. It started in Rails 2,
by the time I arrived on the scene was Rails 3.2, and after a huge amount of work by yours truly
and an excellent offshore team is now on Rails 4.2. Along the way we've updated all the dependencies,
thrown away several, and moved from [Restful Authentication](https://github.com/technoweenie/restful-authentication)
to [Devise](https://github.com/plataformatec/devise) (a process which took far longer than anticipated - I don't recommend it).

I'm planning a move to Rails 5.2 later in 2018, along with finally switching from
[Declarative Authorization](https://github.com/stffn/declarative_authorization) (which has been out of date for years)
to [CanCanCan](https://github.com/CanCanCommunity/cancancan) which is at least maintained, albeit not exactly
the hive of improvement and activity that one might hope for in an authorization framework.

As you might imagine, this process involves an unreasonable amount of time spent reading documentation for the
technologies the company uses and their up-to-date alternatives. The overwhelming conclusion that
I have come to is that ignoring deprecation warnings should be a capital offence. Years' worth of improvements,
bugfixes, security flaws and deprecations can either be incorporated and dealt with piecemeal as they arrive,
or they can be stored up and done all at once when something fundamental forces the change. The former requires
planning and regular allocation of time to clearing up technical debt; the latter requires great impatience
for new features, and a willingness to sacrifice the sanity of whoever might be unfortunate enough to maintain
the software in question.

In many such situations you might find yourself advised "rewrite it in $fashionable_language!". Don't listen, it's
a trap. Unless you're working in Fortran, COBOL, or Visual Basic, whatever you're currently using is very likely
up to the task, and you already know how to use it. There are cases where a switch from one language (e.g. Ruby) to a
lower level one (e.g. a C++ native extension) will be worth it, but these are rarely whole applications
and generally restricted to small places, potentially single functions, where you're CPU bound.
If you set out on a rewrite, you will still need to do all the reading, parsing and comprehension of the existing code
which would be necessary to fix it. That's unavoidable unless you're happy to only recreate the functionality you noticed,
and ignore the bits that were forgotten, overlooked, used only by 5% of your customers, or run once a month.
Once you've done all that work, now you have to throw away all that code you just spent days of your life getting to know,
and start again - or you could just apply that expertise to the code itself and fix the places it's awful.

Some codebases are irrecoverable, but most are just a mess. You don't burn a house down just because someone threw a can of
paint down the stairs, broke all the furniture, and then lived in it with forty cats for a year. On the other hand,
if someone tries to make you live there without giving you time and money to allocate for clearing it up
you are entirely within your rights to make a fuss. The same goes for bad dependencies as for bad code;
a deprecation warning isn't a polite suggestion. It's a boiler that needs servicing, a rotting windowframe.
You might still be functional, you might still be watertight and warm, and the new kitchen table all your guests can see
and use is lovely - but you're storing up expensive trouble for the future.
