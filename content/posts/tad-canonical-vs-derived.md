+++
date = '2026-05-12'
draft = false
title = 'Thinking about Data: Canonical vs. Derived'
+++

This article is part of a series of (ideas for) articles where I muse about a different facet of how one can look at data from a software engineer's perspective. 

We can talk about what it is, but that isn't as much fun as poking and prodding the concept(s) until we come out with some pseudo-philosphical, not-really-poignent, and probably not completely correct proposition when framing data in this light. 

Let's get the boring stuff out of the way:

# What do "canonical" and "derived" mean, in the context of data?

When we're putting words like "canonical" or "derived" in front of the word "data", we're talking about all the following words that mean the same thing: 
    - legitimacy
    - correctness
    - source
    - truth
of the data. When you say this data is from this system of record, that data you are referring to is canonical, so it is the most accurate and correct, relative to every other location that piece of data has been duplicated. 

**Derived** is more or less the opposite; it's a data that was duplicated from somewhere else, possibly transformed in some way to meet the needs of its use. This definition of "derived" is somewhat tricky to wrap your head around on first contact, because when you think derived, you may think of reports and computations.

# What does it really mean then when data is prefixed with "canonical" or "derived"?

One word: Duplication. We're answering the question, "Is this dupliated data, or am I looking at the real thing?"

# Why use duplicated data? Why not fetch from the source every time? 

This may be seen as a bit too reductionist and an oversimplification, but I think it boils down to how efficient it is to fetch the data from the system of record. In an ideal world, a user could fetch the data from the system of record every time they needed it. SORs are generally OLTP systems if they're user-facing. These user-facing systems are generally tuned for the specific data access patterns for the data they hold, which may not be conducive for analytical queries. So duplicating the data has a two-fold impact: less pressure on the database and the opportunity to implement data access patterns that make sense for your business case.