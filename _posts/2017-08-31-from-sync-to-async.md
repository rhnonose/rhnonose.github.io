---
layout: post
title:  "From Sync to Async: How Elixir educated me"
date:   2017-08-31 15:00:00 -0300
---
This post is based on the talk I gave at [ELFBA][elfba] and tells the (hopefully improved) story of how I got into Elixir.

Now it's been a couple of years since I started learning Elixir and almost a year working professionally with it.
The experience overall is awesome and I can't be happier to be blessed doing what I do. Developer experience, productivity, expressiveness and BEAM capabilites just impresses me every day.

But that's not the purpose of this post, but rather the motivation into coming to Elixir in the first place.

## Microservices

The first question marked raised was by microservices. The interest in this topic arose kind of randomly (as it was the [buzzword of 2014][microservices-trend]) and I decided to study more in depth by writing my undergraduate thesis on it. If you checked the related topics, Java is the top match.

As of now we can safely assume that it's a controversial, hyped up topic. [By definition][microservices-def] (which beings with "In short" and it's not) it's not clear-cut and there's no shortcuts to it. But the definition/usage of it is not the highlight here, but rather the problems it proposes to solve: problems with monoliths.

## Problems with Monoliths

Monolith is the default way we develop webapps. That's because what you can say is the minimal infrastructure you can use to run something is a monolith, which you can progress in any way you desire. For that matter, any app or system we build starts like that and usually stays like that for __simplicity__.

Simple is powerful, productive, fast. Attaching a low cost to deliver business value is what made new business grow fast and come up with Prototypes and MVPs. It drove up the popularity of PHP. It helped Rails grow. It even was what Java promised ("write-once-run-everywhere").

The problems come with __growth__. Simplicity is good when it's small and contained. When there's not many features or simple usages, that's the case. Growth can expose a few different types of pains, which we'll outline to see how microservices proposed to solve those issues.

## Availability

The problem with availability occurs when there's too many things connected. If a single module fails and it's a contained, single-purpose piece of code, it can fail from time to time. But in monolithic systems, it happens that everything that is connected to will fail altogether. Time and time again we have to restart the whole system to fix problems in small parts of the system.

This also leads to the releases/deployment problem. Everything has to be shutdown to make a small update, and when the system is big enough that a restart takes too long, business starts to feel the pain. This makes granular releases hard and, consequently, features and bug-fixes take too long to hit production.

A single database is also a consolidated pattern in monolithic apps. The database goes down, so does the entire system.

## Low Productivity

The problem with low productivity is less directly connected. This is generally different from system to system, usually depending on the technology itself. Every language/framework/runtime has its own perks, but usually they all get worsen by the size of the system.

Technical debt is one of them. Fragile modules/components, dead/duplicated code, outdated libraries/frameworks. Since everything lives on the same codebase (usually), refactoring, updating and maintaining everything is a real pain. You could argue that it's not necessarily a problem derived from a monolithic usage, but it gets exacerbated by the fact that everything is connected.

There's then environment differences. Since it's all a single system, copying the entire production is hardly viable. Even the staging doesn't support that amount of data. Extracting small parts of it to make it working in the developer's machiine requires dark magic. There's good tools for that, but even then you get headaches with [heisenbugs][heisenbug].

And when things go wrong when deploying a new release, everything has to be rolledback. It's not only difficult to rollback a release (because of it's size), you have to rollback unrelated features as well, resulting in long downtimes, confusing pipelines and overall unsatisfaction.

Also, with the same root as availability, the long feature cycle time due to those large releases accumulating over time.

## Scalability

Scalability, as mentioned before, could be both technical and organizational.

Technical scalability could be due to bad performance. With cloud computing and on-demand infrastructure, we have the option to scale by copy. This is revolutionary, but also pretty limited to stateless and not granular scaling, and it's also not infinitely scalable (database is still hard to scale by design)

Still on the technical note, code organization is hard to scale. It's hard to modularize everything, and there's pretty much 200 types of design patterns to make readable code, code reuse and best practices, and all of that gets pretty confused when there's too much code. All of that in a single code base, entangled, without clear interfaces or too much boilerplate, things get chaotic fast.

Organizationally speaking, it's hard to split teams. When a single team gets big enough, splitting it is hard when you don't have a clear boundary in the system. Communication overhead is introduces with sub-managers, different tools (e-mail, chat, task management tool, comments on the code) and too many people to talk to without knowing who's responsible for what.

## What's the solution?






[elfba]: http://www.erlang-factory.com/eflba2017/rodrigo-nonose
[microservices-trend]: https://trends.google.com/trends/explore?date=today%205-y&q=microservices
[microservices-def]: https://martinfowler.com/microservices/
[heisenbug]: https://en.wikipedia.org/wiki/Heisenbug
