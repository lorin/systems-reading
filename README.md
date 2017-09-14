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
how to model the world.  This book falls into the former category: about how to
think about problems. He goes into some detail about the imperfect nature of
observation.

Weinberg's a software guy, and so he makes heavy use of discrete models:
finite sets and state representations. This is quite different from Meaadows'
perspective, which uses stocks and flows.

Weinberg summarizes many of the concepts into a pithy set of principles and
laws, with names like:

 * Square law of computation
 * Law of medium numbers
 * Law of conservation of laws
 * Law of happy particularities
 * Law of unhappy particularities
 * Composition law
 * Decomposition law
 * Banana principle
 * Principle of indifference
 * Eye-brain law
 * Generalized Thermodynamics law
 * Lump law
 * Generalized law of complementarity
 * Principle of difference
 * Axiom of experience
 * Principle of invariance
 * Perfect systems law
 * Strong connection law
 * Picture principle
 * Principle of indeterminability
 * Used car law


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

Dekker proposes a new model of thinking about accidents: focus on a holistic
view rather than loooking for a broken part. A fantastic book.

### Reconstructing human contributions to accidents: the new view on error and performance
Sidney Dekker,
Journal of Safety Research 33 (2002) 371-385.

A alternate title for this paper might be "against hindsight". This paper is a
critique of the traditional retrospctive root cause analysis approach to
accident analysis. Instead, it advocates for "human sensemaking":

> The question is not "where did people go wrong?" but "why did this assessment or action make sense to them at the time?

You can see the seeds of "Drift Into Failure" in this earlier paper by Dekker.

He notes the following mechanisms of hindsight:

1. Making tangled histories linear by cherry-picking and re-grouping evidence
1. Finding what people could have done to avoid the accident
1. Judging people for what they did not do but should have done

Dekker advocates scouring the record for the following events and activities:

- shifts in behavior
- actions to influence the process
- changes in the process


Steps to reconstruct concept-dependent account from context-specific incident
data:

1. Lay out the sequence of events in context-specific language
1. Divide the sequence of events into episodes, if necessary
1. Find out how the world looked or changed during each episode
1. Identify people's goals, focus of attention and knowledge active at the
   time.
1. Step up to a conceptual description.


Some quotes from the paper:

- it is critical to understand why people did what they did
- human error is a symptom of trouble deeper inside the system
- safety is not inherent in systems
- human error is systematically connected to features of people, tools, task,
    and operating environment. Progress on safety comes from understanding and
    influencing these connections.
- [effective countermeasures start with] the error-producing conditions present
    in [people's] working environment
- Stressing what was not done (but if it had been done, the accident would not
    have happened) explains nothing about what actually happened, or why.
- The challenge for an investigator becomes to understand how this may not have
    been a discrete event to the people whose actions are under investigation.
- ... this after-the-fact world may have very little relevance to the actual
    world that produced the behavior under investigation.
- Mishaps are more typically the result of everyday influences on everyday
    decision making than they are isolated cases of erratic individuals behaving
    unrepresentatively.
- failures are baked into the nature of people's work and organization
- [failures] are symptoms of deepr trouble or by-products of systemic
    brittleness in the way business is done
- the challenge is to build up an account that moves from the context-specific
    to the context-dependent gradually, leaving a clear trace for others to
    follow, verify, and debate
- The goal is to examine how people's mindset unfolded parallel with the
    situation evolving around then, and how people, in turn, helped influence
    the course of events
- [Process changes] always point to human behavior around them
- [Look for clues] about why actions and assessments made sense to people back
    there and then.
- Accidents do not just happen; they evolve over a period of time.
- Any analysis of human performance has to take the potential for goal conflicts
    into account.
- Goal trade-offs can be generated by the nature of the work itself.
- [A conceptual description] is one of human factors or psychological concepts.
- A crucial way to learn fram failure: discovering similarities between
    seemingly disparate events and even application areas.

### The Language of the System (video)
Rich Hickey,
Feb. 2013

[YouTube link](https://www.youtube.com/watch?v=ROor6_NGIWU)

Hickey is always an engaging speaker. In this talk, he compares and
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
and this book is a kind of generalization of CFEngine's notion of convergence to
more general principles for designing IT-based systems, based on what Burgess
calls promise theory.

I debated whether to even put this book on the list here, as I struggled with
it. There are ideas worth pondering, but the book lacks focus, and the author
meanders across disparate topics without doing a good job tying them into a
unified whole.


### Part Count and Design of Robust Systems
Daniel Frey, Joseph Palladino, John Sullivan, Malvern Atherton,
16th Annual International Symposium of the International Council on Systems Engineering (INCOSE), July 9–14, 2006, Orlando, FL.

[doi:10.1002/sys.20071](http://onlinelibrary.wiley.com/doi/10.1002/sys.20071/full)

Discusses whether reducing part count improves the robustness of a system.
Examines the issue from the perspective of three diffferent theories, and from
three case studies in the domain of gas turbine engines. 

Conclusion: At the component-level, reducing part count has led to
improvements, at the system-level, part count has increased in order to achieve
better reliability, and that the theory of Highly Optimized Tolerance best
captures this phenomenon.

Also, part reductions at the component-level, while they have benefits, also
increase the complexity and coupling of the design and manufacturing stages.

#### Theories

* Theory of Inventive Problem Solving (TRIZ - Russian acronym)
* Axiomatic Design (AD)
* Highly Optimized Tolerance (HOT)

#### Case studies

* Separate blades and rotors versus an integral design
* Blade count reduction in compressor design
* Engine control system

#### Choice quotes

Unique part count is important in systems engineering because it creates
demands on inter-functional coordination and in logistics and supply chain
management

While it has become cliché that greater complexity creates unreliability, the
actual story is more complicated... The essence of this robustness, and hence
of complexity, is the elaboration of highly structured communication,
computing, adn control networks that also create barriers to cascading failure
events (quotes Carson & Doyle).

The theory of Highly Optimized Tolerance suggests that systems will evolve
towards more complexity as robustness demands require countermeasures against
failure modes.

To summarize, although part count reduction is eventually observed at the
component level as suggested by TRIZ, when the scope is enlarged to the system
context, escalating demands for system robustness have generally resulted in
increased number of parts and number of unique parts in jet engines.
