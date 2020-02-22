---
layout: post
title:  "AntifrAGILILITY"
date:   2020-02-21 19:00:00 -0300
categories: agile
---

Recently, I gave a talk on [agile meetup][agile meetup] about something that's been bothering me for a while. This is a post-talk write-up that I intend to expand further.

I've had mixed feelings about agile methodologies for a while and a problem with the agile cargo-culting.
I was never quite certain why since my day-to-day job is mostly technical and I had the luxury of not having to care.
Until recently, for 2 years, I was in a semi-leadership position where I had to care.
Upon reflecting on that experience and reading [antifragile][antifragile], I started making connections everywhere.
My confirmation bias was making me think everything could be explained through this concept, and "agility" wasn't an exception.

To gloss over a bit on the concept, `antifragility` is a recently coined term by [Nassim Nicholas Taleb][taleb] that describes a property of systems that gain from disorder, in contrast to the fragile that loses from disorder and the robust that doesn't care much.
Complex systems such as life, communities, and ecosystem can't be understood in full, but we can measure their fragilities by an asymmetry test: if a system gains more from a stressor than it loses, it's antifragile.

Agile methodologies (or now the bastardized Agile), upon observing from this concept, are methodologies that took advantage of this property.

If you think about software as a system encompassing all stakeholders (from code and machine to clients and investors), it's a system with multiple dependencies, interactions and very complex.
You cannot predict the outcome feasibly [as we intuitively feel sometimes][no estimates], but, drawing from the concepts of antifragility, you can measure some of its properties.

The waterfall method was very risky and fragilized the team/company since the project could be all wrong at the end of a cycle and invalidate all the work done, so the agile methodologies reduced the risk in smaller ones through iterative cycles and feedback.
It introduced stressors to the systems such as recurring requirement changes - and encouraged the team to embrace it - and continuous feedback from the client through collaboration over contract negotiation.
It also recognized that, by letting individuals experiment and fail, it created a loop of constant trial, tinkering, and error.

A lot of the practices may make the system antifragile.
Pair programming shares knowledge and creates redundancy (a push from fragile to robust), increasing the [bus factor][bus factor].
The simplicity principle of reducing unnecessary work also contributes to a more predictable change in the system [via negativa][via negativa].
It also gives autonomy to teams, reducing cascading errors that the entire organization suffers.

From the beginning of the "movement" (when the [manifesto][agile manifesto] was written), the agile methodologies surfaced as a winner in midst of failed other methodologies, so the weaker counterparts had already died.

Self-organization also recognized that top-down control fragilizes the system whereas bottom-up emergence antifragilizes it.
This is why the cargo-culting agile applied top-down rarely works and successful examples come from working with motivated individuals (as the manifesto states).

Lastly, agile principles also apply to individuals, as we can see in programming good practices in general: TDD, incremental paced changes, dead code removal.

Software is code and machine.
This definition would make software at most robust since it's an inanimate artifact.
But software that is constantly maintained gain system properties because of the human interaction (users, maintainers) and, hence, with the proper stressors, can become an antifragile system and [gain from disorder][chaos monkey].

[agile meetup]: https://www.meetup.com/developerparana/events/268765209/)
[antifragile]: https://en.wikipedia.org/wiki/Antifragile
[taleb]: https://en.wikipedia.org/wiki/Nassim_Nicholas_Taleb
[no estimates]: https://ronjeffries.com/xprog/articles/the-noestimates-movement/
[bus factor]: https://en.wikipedia.org/wiki/Bus_factor
[via negativa]: https://en.wikipedia.org/wiki/Antifragile#Via_negativa
[agile manifesto]: https://agilemanifesto.org/
[chaos monkey]: https://netflix.github.io/chaosmonkey/
