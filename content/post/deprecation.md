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

This is commonly referred to as 'technical debt'. Occasionally someone brings up the slightly more precise suggestion
that it should be referred to as a 'technical unhedged call option'. While financial analogies are not perfect nor are
comparisons to buildings and excessive feline collections, so we just have to make do with what we've got.

There are many forms of debt, some worse than others. Some, like the mountains of poor code you write at 3am to get
your startup off the ground, can be mostly helpful. Think of it like a mortgage - you're in debt, you will need to
pay it down, but it gives you leverage you could otherwise never dream of. The same happens with big projects; you
and your team will code quickly and as well as you can under the circumstances, and it might not be the best or most
well organised code, but it does the job and people buy the product. As long as you don't forget to allocate the time
to come back and refactor it later to pay it down, you'll be fine.

Another kind of debt is the tests you don't write and the comments you leave out. This is more like credit card debt
or payday loans than anything else. It grows daily as you work, and the payments are frequent and get worse with every iteration.
Every change you make that breaks an untested function elsewhere, every hour you spend poring over code trying to work
out what they last person to edit it was trying to achieve, is time from both your life and the pocket of whoever's paying
for whatever you're working on.

The final kind is the unhedged call option. This is the code you think you'll write once, and perhaps never touch again. Scripts
which do something important but are only needed once a year. Small projects you hope to move on from. New features you're
not sure about but which underpin something larger that you need to get to. Ignored deprecation warnings and outdated
dependencies. You might never need to pay this back. You could be fine for _years_ without suffering the consequences
of poor code and infrequent dependency updates. The market moves, however, and eventually you get unlucky. Perhaps a new
technology you need is incompatible with parts of your codebase. Perhaps there's a known major security vulnerability in a
library on which your entire application depends.

Whatever it is, suddenly you have to do all the work that should have been done over time to keep these things cleaned up and
up to date, but you have to do it _right now_. Before the next feature can go live. Perhaps before anyone notices you're
vulnerable and steals your entire customer database. So you spec the work, and discover that your codebase has called in
its option on that work, and the price is now six to twelve months of your entire team doing absolutely nothing else whatsoever.
No features. No projects. Bugfixes galore because you might as well while the refactoring is going on, but nothing that feels
'productive'. How much do you spend on salaries for your dev team? The bad news is that not keeping up with your dependencies
just cost you six figures, but the good news is that half of them will quit in disgust when they realise what you're asking
them to do, so you can save half of it.

Do the projects, accumulate the debt; there's no other way to do business. Just don't forget that one day, you will have to
pay it down, and that will hurt a hell of a lot more if you haven't made either payments or a sinking fund.
