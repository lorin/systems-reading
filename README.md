# Systems and failure reading list

This page contains references to books and papers about complex systems and how
they fail. I'm interested in how these relate to software systems, so my
comments will be biased in that direction.

You may also be interested in my [availability reading list][1], which covers
more practical details of how to build highly available systems.

[1]: https://github.com/lorin/availability-reading

### To Engineer Is Human: The Role of Failure in Successful Design
Henry Petroski,
Vintage,
1992.

Petroski's big idea is that the field of engineering only advances because of
failures. If a building stays up, we don't get any information about whether the
building was actually designed and built correctly. However, if it collapses, we
know for certain that there was a flaw somewhere.

As a consequence, when there are no failures, engineers will push the boundaries
over time until a failure happens, and then the engineering community learns
from the failure and takes the failure mode into account in future designs.

Unfortunately, the types of failure retrospectives that happen in civil
engineering don't happen in IT at the community level. Yes, these retrospectives
do happen inside IT organizations, but we don't have the same kinds of
mechanisms for sharing these lessons in the wider community.

### How Complex Systems Fail
Richard I. Cook,
Cognitive Technologies Laboratory,
University of Chicago,
Revision D (00.04.21)

[pdf](http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf)

Cook presents eighteen observations about systems. It's tempting to simply
reproduce them all here, but a few examples should suffice to give a sense of
the paper:

* Complex systems run in degraded mode.
* All practitioner actions are gambles.
* Change introduces new forms of failure.

This essay is also reproduced as chapter 7 in "Web Operations: Keeping the Data
on Time" by O'Reilly Press.


### Normal Accidents: Living with High-Risk Technologies
Charles Perrow,
Princeton University Press,
1999.

Perrow talks about the failure modes of complex systems whose behaviors cannot
be fully understood by human operators, with much discussion about nuclear power
plants.


### An Introduction to General Systems Thinking
Gerald M. Weinberg,
Dorset House,
2001.

There seem to be two schools of thought on the idea of "systems thinking". One
of the schools is about how to think about problems, and the other one is about
how to model the world.

This book falls into the former category: about how to think about problems.
From Weinberg's perspective, systems thinking is a holistic, organic approach
to thinking about problems, as opposed to a reductionist, analytic approach.


### The Systems Bible: The Beginner's Guide to Systems Large and Small
John Gall,
General Systemantics Press,
2003.

Written by a pediatrician and originally published in the 1970s, this book is
written as a collection of axioms about the behaviors (or, less charitably,
pathologies) of complex systems. Examples of such axioms include:

* Fundamental theorem: New systems generate new problems.
* The naming fallacy: the name is most emphatically not the thing.
* The jet travel paradox: when you get there, you're still not there.

Although originally written decades before the emergence of web-based Internet
services, the concepts are surprisingly applicable.

### Report of Columbia Accident Investigation Board
Aug 26, 2003.

[link](http://www.nasa.gov/columbia/home/CAIB_Vol1.html)

This is NASA's post-mortem report on the Space Shuttle Columbia accident. It is
a surprisingly readable document that describes the incident and contributing
factors.


### Thinking in Systems: A Primer
Donella H. Meadows,
Chelsea Green Publishing,
2008.

Meadows's book falls into the "how to model the world" category of systems
thinking book. She discusses how to model complex systems in terms of constructs
like buffers and feedback loops.

I remember people used to say how computer programs behave differently from
physical artifacts. And, yet, distributed software systems *do* behave like
other types of systems. You can expend resources (e.g., memory, disk space),
there are couplings and feedback loops that can cause all sorts of interesting
systems-like behaviors.

### Drift into Failure
Sidney Dekker,
Ashgate,
2011.


This book is very popular in the DevOps community. I must admit that I haven't
read it yet.


### The Language of the System (video)
Rich Hickey,
Feb. 2013

[YouTube link](https://www.youtube.com/watch?v=ROor6_NGIWU)

Hickey is alwways an engineering speaker. In this talk, he compares and
contrasts how we build programs with how we build systems.


### Antifragile: Things That Gain from Disorder
Nassim Nicholas Taleb,
Random House,
2014.

The big idea of this book is that there are some systems that acutally get
better when exposed to doses of damage.


### In Search of Certainty
Mark Burgess,
O'Reilly Media,
2015.

Burgess is the author of the venerable CFEngine configuration management system,
and this book is a kind of generalation of CFEngine's notion of convergence to
more general principles for designing IT-based systems, based on what Burgess
calls promise theory.

I debated whether to even put this book on the list here, as I struggled with
it. There are ideas worth pondering, but the book lacks focus, and the author
meanders across disparate topics without doing a good job tying them into a
unified whole.




