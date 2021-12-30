# Systems and failure reading list

This page contains references to books and papers about complex systems and how
they fail. I'm interested in how these relate to software systems, so my
comments will be biased in that direction. In particular, the
[availability](#availability) section is specific to high availability
in distributed systems.

If you're interested in resilience engineering, check out my [resilience engineering notes](https://github.com/lorin/resilience-engineering).

Mark McGranaghan maintains a [services engineering reading list][1] with some
significant overlap.

[1]: https://github.com/mmcgrana/services-engineering

## Systems in general


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

[Link](https://how.complexsystems.fail/)

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
computing, and control networks that also create barriers to cascading failure
events (quotes Carson & Doyle).

The theory of Highly Optimized Tolerance suggests that systems will evolve
towards more complexity as robustness demands require countermeasures against
failure modes.

To summarize, although part count reduction is eventually observed at the
component level as suggested by TRIZ, when the scope is enlarged to the system
context, escalating demands for system robustness have generally resulted in
increased number of parts and number of unique parts in jet engines.

### Ironies of automation
Lisanne Bainbridge,
Automatica,
Volume 19, Issue 6, November 1983, Pages 775-779.
<https://doi.org/10.1016/0005-1098(83)90046-8>

Bainbridge describes how the adopting automation can increase the occurence of
incidents.

Design errors in the automation system can be a major source of operating problems.

As automation increases, operators have less experience, and therefore when
they need to take over, they are more likely to make a mistake.



### Resilience is a verb

David D. Woods, 2018,
In book: IRGC resource guide on resilience (vol. 2): Domains of resilience for complex interconnected systems,
Publisher: EPFL International Risk Governance Center,
<https://www.researchgate.net/publication/329035477_Resilience_is_a_Verb>

Resilience refers to a system's capacity to adapt to unforeseen surprises (SNAFUs) that result from breakdowns
in standard plans and automation.

This includes capacity:

* to anticipate - see signs of trouble ahead and adapt early
* to synchronize - adjust how different roles at different levels coordinate
* to be ready to respond - developing response capabilities that can be
  deployed and mobilized
* for proactive learning - learning about brittleness and sources of resilient
  performance

Four capabilities provide the basis for continuous adaptation:
* *Initiative*  
* *Reciprocity* across roles and levels
* Tangible experiences of surprise 
* Proactive learning from well-handled surprises

Key terms: resilience, adapt, adaptive capacity, SNAFUs, SNAFU catching,
anticipate, synchronize, proactive learning, initiative, reciprocity, tangible
experiences, plans, goals

Notable quotes:

* Resilience is about what a system can do
* Resilience concerns the capabilities a system needs to respond to inevitable
  surprises
* system has some ability to recognize when it's adequate to continue the plan,
  to continue to work in the usual way, and when it is not adequate to continue
  on, given the demands, changes and context ongoing or upcoming.
* resilient performance depends on the ability to adapt outside of the standard
  plans as thse inevitably break down.
* All organizations are adaptive systems, consist of a network of adaptive
  systems, and exist in a web of adaptive systems.
* The pace of change is accelerated by past successes
* As scale and interdependencies incrase, a system's performance on average
  increases, but there is also an increase in the proportion of large
  collapses/failures.
* Adapating to handle the regular occurence of SNAFUs makes the work of SNAFU
  Catching almost invisible.
* For onganizations to flourish, they need to build and sustain the ability to
  *continuously adapt*.
* Organizational systems succeed despite the basic limits of automata and plans
  in a complex, interdependent and changing environment because responsible
  people adapt to make the system work despite tis design — SNAFU Catching.
* The pressures constrain and direct how the expression of initiative
  *prioritizes* some goals and *sacrifices* other goals when conflicts across
  goals intensify.
* tangible experiences of surprise are powerful drivers for learning how to
  guide adaptability.
* proactive learning from well-handled surprises contributes to re-calibration
  and model updating.
* Reslience is a verb that refers to capabilities that build and sustain the
  potential for continuous adaptability.

### Four concepts for resilience and the implications for the future of resilience engineering

David D. Woods,
Reliability Engineering and System Safety,
Volume 141, September 2015, Pages 5-9,
<https://doi.org/10.1016/j.ress.2015.03.018>

[pdf](https://www.researchgate.net/publication/276139783_Four_concepts_for_resilience_and_the_implications_for_the_future_of_resilience_engineering)

Woods argues that the term *resilience* is overloaded. He outlines four commonly used meanings:

1. rebound (response to surprises)
2. robustness (increased ability to absorb pertubations)
3. graceful extensibility (how systems stretch to handle surprises)
4. sustained adaptability

Woods defines a *surprise* as a disturbance to the system that is outside of the envelope of
events that the system can normally handle.

#### Rebound

Rebound refers to the ability of a system to recover after a surprise.
In this defintion, more resilient systems are better able to recover from surprises.

#### Robustness

Robustness refers to the set of disturbances that the system can respond to
effectively. In this definition, more resilient systems can gracefully respond to a
larger set of disturbances (i.e., fewer of these disturbances are surprises).

Woods criticizes robustness because it says nothing about what happens to a
system when it encounters a surprise. A system may be resilient by this
definition and yet utterly collapse when faced with a surprise. (He uses the
phrase *brittle at its boundaries*).

Woods also points out that as the performance envelope of a system widens,
it may become vulnerable to new kinds of events.

#### Graceful extensibility

Graceful extensibility refers to the ability of a system to change itself in order
to better handle the different kinds of surprises that it may face in the
future. He uses the term *stretching*, asking *how do systems stretch to handle
surprises?* 

An extended quote:

> Systems with high graceful extensibility have capbilities to anticipate
> bottlenecks ahead, to learn about the changing shape of disturbances and
> possess the readiness-to-respond to adjust responsies to fit the challenges.

The above quote makes it sound like this concept is proactive, but Woods notes
that:

> [S]urprise has regular characteristics as many classes of challenge re-cur
> ... which can be tracked and used as signals for adaptation.

Woods contrasts graceful extensibility with what he calls *brittleness*,
defined as *how rapidly a system's performance declines when it nears and
reaches its boundary*.

#### Sustained adpatability

Sustained adaptability refers to systems that are flexibile enough to adapt over long time
scales. Woods claims that this type of resilience requires that the system
have a *layered network* architecture, (a necessary but not sufficient
condition). He argues that a system needs this type of architecture early
in its life cycle in order to be able to adapt to changes across the system's life cycle.
Even as the system adapts, it will preserve certain architectural principles
that provide it with the ability to adapt.

Woods asks the following questions of such systems:

1. What governance or architectural characteristics explain the difference
between networks that produce sustained adptability and those that fail to
sustain adaptability?
2. What design principles and techniques would allow one to engineer a network
that can produce sustained adaptability?
3. How would one know if one succeeded in their engineering?

Ultimately, Woods argues that *rebound* and *robustness* concepts have proven to be less useful 
He emphasizes the value of *graceful extensibility* and *sustained adaptability*.

## Availability

### Why Do Computers Stop and What Can Be Done About It?
Jim Gray,
Tandem Computers,
Technical Report 85.7
June 1985,
PN87614

[pdf][gray85]

Describes strategies for achieving good reliability and availability in the
presence of faults.

Notable quotes:

* System administration, which includes operator actions, system configuration, and system maintenace was the main source of failures -- 42%. p8

* The top priority for improving system availability is to reduce administrative mistakes by making self-configured systems with minimal maintenance and minimal operator interaction. p12

* A way to improve availability is to install proven hardware and software, and then leave it alone. p13

* If you consider an industrial sofwtare system which has gone through structured
design, design reviews, quality assurance, alpha test, beta test, and months or
years of production, then most of the "hard" software bugs, ones that always
fail on retry, are gone. *The residual bugs are rare cases, typically related to
strange hardware conditions (rare or transient device fault), limit conditions
(out of storage, counter overflow, lost interrupt, etc,, or race conditions
(forgetting to request a semaphore)*.  p17-18 (emphasis mine).

* Dealing with system configuration, operations, and maintenance remains an unsolved problem. p32

### Making Reliable Distributed Systems In The Presence Of Software Errors
Joe Armstrong,
PhD Dissertation,
Royal Institute of Technology,
Stockholm, Sweden
Decmeber, 2003

[pdf][armstrong03]


Describes both Erlang and principles for using it to build reliable systems.

### Release It!: Design and Deploy Production-Ready Software
Michael Nygard,
Pragmatic Bookshelf,
April, 2007

### On Designing and Deploying Internet-Scale Services
James Hamilton,
Proceedings of the 21st Large Installation System
Administration Conference (LISA '07),
November 11-16, 2007

[html][hamilton07]

Even though this paper was written before cloud computing became widely adopted
(the word "cloud" does not appear once), it feels as if it could have been
written today. The only other indications of it being a little are a discussion
of hardware, and a proposed deployment cycle of three months.

### Web Operations: Keeping the Data on Time
John Allspaw & Jesse Robins, eds.
O'Reilly Media,
July 2010

A collection of essays.


### Simple Testing Can Prevent Most Critical Failures: An Analysis of Production Failures in Distributed Data-Intensive Systems

Ding Yuan, Yu Luo, Xin Zhuang, Guilherme Renna Rodrigues, Xu Zhao, Yongle
Zhang, Pranay U. Jain, and Michael Stumm
Proceedings of the 11th USENIX Symposium on Operating  Systems Design and Implementation (OSDI '14)
Oct. 2014.

[pdf][yuan14]

An empirical study that explores the reasons why distributed systems
fail in production by analyzing the root causes of around 200 confirmed system
failures. You can read [my review](http://neverworkintheory.org/2014/10/08/simple-testing-can-prevent-most-critical-failures.html) of this paper at *It Will Never Work In Theory*.

I also wrote more details on this paper [here](yuan14.md)

### An Analysis of Network-Partitioning Failures in Cloud Systems
Ahmed Alquraan, Hatem Takruri, Mohammed Alfatafta, and Samer Al-Kiswan
Proceedings of the 13th USENIX Symposium on Operating Systems Design and Implementation (OSDI ’18).
Oct. 2018

[pdf][alquraan18]

An empirical study that demonstrates how many open source distributed systems
(including Cassandra, Zookeeper, Mesos, Chronos, Kafka, Redis, Riak, and RabbitMQ) fail badly under network partitions.

The authors built [NEAT](https://dsl.uwaterloo.ca/projects/neat/), a tool for
injecting network partitions, in order to do these their testing.

The findings:

1. A large percentage (80%) of the studied failures have a catastrophic impact, with data loss being the most common (27%) 
2. The majority (90%) of the failures are silent, whereas the rest produce warnings that are unatonable
3. Twenty one percent of the failures lead to permanent damage to the system. This damage persists even after the network partition heals.
4. Leader election, configuration change, request routing, and data consolidation are the most vulnerable mechanisms to network partitioning.
5. The majority (64%) of the failures either do not require any client access or require client access to only one side of the network partition.
6. While the majority (69%) of the failures require a complete partition, a significant percentage of them (29%) are caused by partial partitions.
7. A majority (83%) of the failures triggered by a network partition require an additional three or fewer input events to manifest.
8. All of the failures that involve multiple events only manifest if the events happen in a specific order.
9. The majority (88%) of the failures manifest by isolating a single node, with 45% of the failures manifest by isolating any replica. 
10. The majority (80%) of the failures are either deterministic or have known timing constraints.
11. The resolution of 47% of the failures required redesigning a system mechanism.
12. All failures can be reproduced on a cluster of five nodes, with the majority (83%) of the failures being reproducible with three nodes only.
13. The majority of the failures (93%) can be reproduced through tests by using a fault injection framework such as NEAT.

### Notes on Distributed Systems for Youngbloods
Jeff Hodges,
Something Similar blog,
January 14, 2013

[html][hodges13]

General advice from a Twitter engineer about the challenges of developing and
debugging distributed systems. He also gave an excellent talk at RICON West 2013
entitled [Practicalities of Productionizing Distributed Systems][hodges13-talk]
that is well worth your time.


### Fault Injection in Production: Making the case for resiliency testing
John Allspaw,
ACM Queue, Volume 10, issue 8,
August 24, 2012

[html][allspaw12]

Allspaw argues that you must observe the system tolerating failures in
production in order to have confidence in the system's resiliency. He discusses
fault injection in the context of GameDay exercises at Etsy. Although the essay
does not mention Chaos Monkey, it provides a strong motivation for tools similar
to Chaos Monkey.

### The Error Model
Joe Duffy,
Joe Duffy's Blog,
February 7, 2016

[html][duffy16]

Duffy talks about the error model that they used in the
[Midori](http://joeduffyblog.com/2015/11/03/blogging-about-midori/) language.
Interesting content about how to handle errors in code.

### A New Accident Model for Engineering Safer Systems
Nancy Leveson,
Safety Science, Vol. 42, No. 4, April 2004

[pdf][leveson04]

Leveson proposes a model of accidents called STAMP: systems-theoretic accident
model and processes. STAMP focuses on identifying safety constraints that were
violated and determining why the controls were inadequate.

While this paper is focused on software safety, it is still relevant for
availabilty, since an outage can be viewed as an accident.

### Why do Internet services fail, and what can be done about it?
David Oppenheimer, Archana Ganapathi, and David A. Patterson,
4th Usenix Symposium on Internet Technologies and Systems (USITS ‘03), 2003.

[pdf][oppenheimer03]

Oppenheimer et al. did a case study of three Internet services to determine
common causes of failures. Findings incldue:

* Front-end machines are a significant source of failure, largely due to operator
  configuration errors.
* Operator error is the leading cause of service failure in two of the three services.
* Operator error was generally due to misconfiguration rather than procedural
  errors.
* Operator error generally arose when operators were making changes to the system.
* Networking problems were a significant cause of failure.

Networking problems are difficult to mask because:

* networks are often a single point of failure
* network failure modes tend to be complex

Proposed techniques for avoiding or mitigating failures, in decreasing order of
impact:

 * Online correctness testing
 * Thoroughly expose and monitor for software and hardware failures
 * Redundancy
 * Config. checking
 * Online fault/load injection
 * Component isolation
 * Pre-deployment fault/load injection
 * Proactive restart
 * Pre-deployment correctness testing

### I want to believe: some myths about the management of industry safety
Denis Besnard, Erik Hollnagel,
Cognition, Technology and Work, Springer Verlag, 2014, 16 (1)

[pdf][besnard14]

The authors discuss five myths about safety and propose revisions.

#### Human error

Myth: Human error is the largest single cause of accidents and incidents

Revision: 'Human error' is an artifact of a traditional engineering view, which
treats humans as if they were (falliable) machines and overlooks how performance
adjustments are used to match activities to the working conditions.

#### Procedure compliance

Myth: Systems will be safe if people comply with the proedures
they have been given.

Revision: Actual working situations usually differ from what the procedures
assume and strict compliance may be detrimental to both safety and efficinecy.
Procedures should be used carefully and intelligently.

#### Protection and safety

Myth: Safety can be improved by barriers and protection;
increasing the layers of protection leads to higher safety.

Revision: Technology is not value netural. Additional prteoction changes
behaviour so that the intended safety improvements might not be obtained.

#### Mishaps and root causes

Myth: Root cause analysis can identify why mishaps happen
in complex socio-technical systems.

Revision: Human performance cannot be described as if it was bimodal. In
socio-technical systems, things that go wrong happen in the same way as things
that go right.

#### Accident investigation

Myth: Accident investigation is the logical and rational
identification of causes based on facts.

Revision: Accident investigation is a social process, where causes are
constructed rather than found.

#### Safety first

Myth: Safety always has the highest priority and will never be
compromised.

Revision: Safety will be as high as affordable — from a financial and ethical
perspective.

## Hints for Computer System Design
Butler W. Lampson,
ACM SIGOPS Operating Systems Review,
Volume 17 Issue 5, October 1983

[pdf][lampson83]

General advice on building system, based on the author's experiences building
several systems at Xerox PARC. It's all still relevant, but here are some
quotes I found particularly notable:

Defining interfaces is the most important part of system design.

Interface design must satisfy three conflicting requirements:

1. An interface should be simple
2. An interface should be complete
3. An interface sould admit a sufficiently small and fast implementation

Do one thing at a time, and do it well.

Don't generalize; generalizations are generally wrong.

Neither abstraction nor simplicity is a substitute for getting it right.

The purpose of abstractions is to conceal *undesirable* properties; desirable
ones should not be hidden.

*Use procedure arguments* to provide flexibility in an interface (support
functions as arguments).

Keep basic interfaces stable.

Even when an implementation is successful, it pays to revisit old decisions as
the system evolves; in particular, optimizations for particular properties of
the load or the environment (memory size, for example) often come to be far
from optimal.

*Use a good idea again* instead of generalizing it.

Handle normal and worst cases separately as a rule.

In allocating resources, strive to avoid disaster rather than to attain an
optimum.

We learned that the only important thing is to avoid thrashing.

The most successful schemes give a fixed share of the cycles to each job and
don't allocate more than 100%.

Shed load to control demand, rather than allowing the system to become overloaded

End-to-end: Error recovery at the application level is absolutely necessary for a reliable
system, and any other error detection or recovery is not logically necessary
but is strictly for performance.

Two problems with the end-to-end strategy:

1. It requires a cheap test for success
2. It can lead to working sytems with severe performance defects that may not
   appear until the system behcomes operational and is placed under heavy load.

Log updates to record the truth about the state of an object.

## End-to-end Arguments in Systems Design
J.H. Saltzer, D.P. Reed and D.D. Clark,
ACM Transactions on Computer Systems (TOCS),
Volume 2 Issue 4, Nov. 1984 

[pdf][saltzer84]

Proposes that functionality guarantees must be implemented on an end-to-end
basis, rather than by simply building on top of some infrastructure that
provides guarantees.

The example given in the paper is that if you want to ensure that file transfer
is reliable, you have to do an end-to-end check to verify that the transfer
succeeded, because there are failure points other than at the levels of
infrastructure you build on that can provide guarantees.

## The Mathematical Disposition of Structural Engineers

Julie Gainsburg,
Journal for Research in Mathematics Education
Vol. 38, No. 5 (Nov., 2007), pp. 477-506,
DOI: 10.2307/30034962

This paper describes an ethnographic study of structural engineers to
understand how they use mathematics. She introduces the idea of *skeptical
reverence*.

[pdf (paywalled)][gainsburg07]

Quotes from paper:

Students come to see mathematics as a rule-driven, linear, solitary,
school-only activity, in which problms have one correct solution that should be
quickly evident, and true understanding requires special talent.
...mathematics is about understanding, sense-making, communicating, and
discovering patterns; that mathematics is collaborative; and that people with
differing backgrounds, talents, and perpsectives-including children- can and
should participate in it.

...many mathematicians do not hold the view that every child can and should
participate in authentic mathematical activity.

Traditional efforts to demonstrate mathematic's real-world utility take the
form of "word problems" that thinly disguse mathematial exercises in real
contexts; these contrived problems do little do sitrub student's view of
mathematics as a school-only activity.

More often, problems arose because the complexity and uniqueness of each
building precluded the simple application of easablished procedures.

Engineering theory and methods had to be adapted to each new project in ways
not immediatley evident, and for much of the work I observed, no established
procedures were available.

... structural engineering work is by nature iterative.

The most intractable problems I observed stemmed from what I came to see as the
fundamental problem of structural engineering: that the phenomena at the center
of the engineer's work (the structure and their behaviors) were nonexistent or
inaccessible.

Structural engineering is a bootstrapping process. The engineer makes initial
rough design assumptions to get started, then design and analysis inform each
other as they converge to a final state through repeated iteration.

Unfortunately, an empirical test of the "correctness" fo the design or analysis
is rarely possible.

[A design] also had to be justifiable on the bases of feasibility, available
materials, labor capacity, budget, and time, as well as on the less tangible
but arguably more crucial grounds that the design solution and the method that
yielded it made sense and "felt" good" to the engineer.

In some sense, the engineers equated engineering with the exercise of
engineering judgment: at least, what inspired engineers to identify colleagues
as expert had more to do with the ability to make judgments than to apply and
perform mathematics.

As did the engineers I observed, Vick concluded that engineering judgment was
virtually synonymous with expertise.

Kinds of decisions:
* Determining what is a good or precise enough calculation or estimation
* Making assumptions or simplifications to be the baes of mathematical models
* Overriding mathematically "proven" results
* Determining appopriate uses of technology tools
* Assigning qualittive factors (e.g., soil type) and applicable conditions for
  selecting formulas
* Overriding official building codes
* Discretizing (grouping elemtns to reduce the number of types to be designed)


Engineering judgment often entailed a nonmathematical decision about a
situation that could not be adequately mathematized; that is, it sometimes
replaced mathematical resources, bridging unmathematizable gaps in the analytic
process.

...engineering judgement had no recourse to proof; it could not be verified.

Again, there were no established rules to guide these sorts of decisions, yet
they had to be made well. The consequences of poor judgment here ranged from
increased time and cost to catastrophic structural failure.


In this episode, Micahel resorted to engineering judgment to determine his
degree of trust in the results of their mathematical modeling and what to do
when that trust was shaken.

On occasion, they even rejected proven results that they felt were dedutivley
sound, because they were impractical. In these cases, the engineers relied on
judgment to convince themselves that ocerriding the proof would be safe and
justifiable.

Proof, however, is not always possible. For example, at one point Michael and
Ray were forced to exercise judgment when no mathematical method was available.

The concept of engineering judgment reifies the process of prioritizing and
selecting among these resources, task by task, and I contend that engineering
judgment, rather than mathematics, is hegemonic over the practice of structural
engineering.

Mathematics enables anlaysis, but analysis can only be retrospective.
Matheamtical theories and methods do not point to particular designs or best
methods of analysis and so cannot serve as the ultimate authority for
engineering work.

The structureal engineers' mathematical point of view appears to be one of
skeptical reverence-matheamatics is a powerful and necessary tool that must be
used judiciously and skeptically.


The end products of structural work are a symbolically expressed design and a
story about how that design came to be.

That story .... erases nearly all traces of iterations, missteps, and rejected
methods...

The new official story presented to building officials, owners and contractors is straightforward, linear, and rational, aimed to create the impression that the design solution was the inevitable consequence of the constraints and the theory, that the analysis took the only logical route, and that the process
unfolded unimpeded, step by predictable step.

He admitted to using computerized anlyses, post hoc, to justify solutions he
had attained using "classical" (approximation) methods:

Practically speaking, could I get it through a city building department? No...
Could I get it through a peer reviewer? No. Everyone in the industry believes
in computers. So the issue for me, the challenge, is to make the computer come
up with the right answer. I use all the classical methods to figure out what
the answer ought to be, and then I use that figure to figure out exactly how
I'm going to arrange my model.

So I think that over-reliance on a mathematical process actually obscures the fundamental nature of the behavior you're trying to describe.

Matehmatics is fundamental to solving structural engineering problems.

People may be more inclined to use mathematics, and in more effective ways, in
everday life and work if their school training acknowledged that "doing
everyday math" larbely means deciding how, when and when not to use
mmathematics, and if they were offered opporutnities to make and reflect on
such decisions.

authentic problems from high-tech professions are usually inapporpriate for the
classroom, for practical reasons and because students lack athe domain
knowledge to make judgments about the use of mathematics and other resources.

A worthy challenge for mathematics educators is to make the matehamtical
products of professional engineersa nd scientists accessible to students for
analysis, even if sttudents are incapable of producing such work
themselves.


## Underground adaptations: case studies from health care
Shawna J. Perry, Robert L. Wears
Cognition, Technology & Work,
Vo. 14, Iss. 3 (Sept. 2012), pp. 253-260
DOI: 10.1007/s10111-011-0207-2
[pdf (paywalled)][perry12]

Two observational case studies about new technologies that were introduced into
hospital emergency departments:
* electronic charts (replacing paper charts)
* digital status board (replacing a white board)

In both cases, the replacement technology did not accomodate all of the work
that the doctors were doing with the previous technologies, and so the doctors
adapted by using workarounds ("shadow" paper charts, using both old white board
and new digital status board, carrying papers around). There was work that
suffered due to the introduction of the new technology.

They summarized their findings as:

* Articulated functions aren't the same as important functions
* No change is without unintended effects
* Apparent success is not a sign of success
* Need to support exceptions
* Dynamic environments require dynamic designs

### Risk Management in a dynamic society: a modeling problem
Jens Rasmussen,
Safety Science,
Vol. 27, No. 2/3, (1997), pp 183-217
DOI: 10.1016/S0925-7535(97)00052-0
[pdf (paywalled)][rasmussen97]

In this widely cited paper, Rasmussen advocates for a cross-disciplinary,
systems-based approach to thinking about how accidents occur. He argues that
accidents occur because the system migrates across a dangerous boundary, and
this migration occurs during the course of normal work.

This paper contains the seeds of Woods's notion of the adaptive universe,
Dekker's notion of drift, and Leveson's notion of control-theoretic
systems-based approach to safety.

In particular, he proposes the following risk management framework for
control of safety in a socio-technical system (section 2):

![Risk management framework](risk-management-framework.png)

He relates accidents to the notion of a system moving towards a boundary
(section 6):

![Movement to the boundary](boundary.png)

#### Terms
- Systems approach
- Control-theoretic
- decisions, acts, and errors
- hazard source
- anatomy of accidents
- energy
- systems thinking

#### Selected quotes by section

1. Introduction
    - often found that attempts to improve safety of a system from models of local features were
    compensated by people adapting to the change in an unpredicted way
    - control structure embedded in an adaptive social-technical system
2. The problem space: risk management in a dynamic society
    - safety depends on control fo work processes to avoid accidenta side effects causing harm
3. The present dynamic society
    - very fast pace of change of technology
    - scale of industrial installations is steadily increasing
    - rapid development of information and communication technology
    - very aggressive and competitive environment
4. Modeling by structural decomposition: tasks, acts and errors
    - aim of commercial companies change toward narrow focus on financial
      operations
    - need more studies of vertical interaction among levels of socio-technical
      systems
    - traditional approach:
        * system decomposed into structural elements
        * behavior decomposed into events
        * behavior decomposed into decisions
    - rules are inadequate to handle all situations
    - rules, laws, and instructions parctically speaking are never followed to the
      letter
    - even in nuclear power operation, modification of instructions repeatedly
      found
    - easy for accident investigators to find rule violations in hindsight
    - difficult for researchers to isolate proper decisions in context
    - see: naturalistic decision making
    - successful orgs operate at fringes of usual, accepted practice
5. Accident causation
    - accidents are caused by systemic migration of org behavior toward accident under influence of
      pressure toward cost-effectievness in aggresive, compettitive environment
6. Modelling by functional abstraction: migration toward the boundary
    - natural migration of activities toward boundary of acceptable performance
    - during adaptive search, actors have ample opportunitty to identify 'an effort
      gradient'
    - management will normally supply an effetive 'cost gradient'
    - result: systemic migration toward the boundary of functionally acceptable
      performance
    - if crossing boundary is irreversible, error or accident may occur
    - defense-in-depth: local violation of one of the defense has no immediate,
      visible effect
    - defense likely to degenerate systematically through time
    - explanation of accident in terms of events, acts, & errors not very useful
      for design of improved systems
    - new apporach to representing system behavior: mechanisms generating behavior in actual, dynamic work context
    - analogy: thermo-dynamic models:
        * boundary conditions
        * gradients of a field
7. Control of system performance
    - old: fighting deviations
    - new:
        * make boundaries explicit and known
        * give opportunitites to develop coping skills at boundaries
    - increase margin from normal operation to loss-of-control boundary
    - increase awareness of boundary: instruction & motivation campaigns
    - safety culture only works as long as acts as *continuous pressure* compensating
      the *functional pressure* of work environment
    - most promising general approach: 
        * explicit identification of boundaries of safe operation
        * efforts to make boundaries visible to actors
        * give actors opportunity to leran to cope with the boundaries
8. Risk management: a control task
    - risk management to be considered a control function
    - focused on maintaining particular hazardous, productive process within
      boundaries of safe operation
    - systems approach based on control theoretic conepts should be applied to
      describe overall systems function
    - studies of risk management must be based on categorisation of hazard sources according to their control requirements
    - all decision makesrs are busy managing their particular work  domains and
      their attention will be ofucsed on the control of the means and ends of their
      normal productive tasks while they strive to meet their production targtes,
      often under considerable stress to optimise process criteria such as time
      spent and cost-effectiveness.
    - accidents are created by the interactio of potential side effects of the
      performance of several decison makers during their normal work
    - performance critieria in actual work are very often implicit in company or
      local work practice, difficult tomake explicit
    - no control system will perform better than its measuring channel
    - analyze requirements and constraints of problem space, formulated at
      several levels of a means-ends hierarchy
9. Identification of constraints and safe boundaries
    - contrasts frequent, small-scale accidents with rare, large-scale accidents
    - proposes development of classification system for hazard sources & their
      different control requirements:
        * nature of significant hazard source to control
        * anatomy of accidents following release of hazard
    - research calls for cross-disciplinary competency
10. Present trends in the paradigms of human sciences
    - behavior of dynamic socio-technical ssytem cannot be represented in terms
      of task sequences and errors referring to a 'correct' or 'rational'
      performance
    - traditional description of human behavior
        * identification of rational behavior by normative models
        * actual behavior described in terms of deviation/error wrt normative behavior
    - current trend: model actual behavior in terms of behavior shaping
      constraints of env't & adapative mechanisms of human actors in env't
    - surveys models: 
          1. normative (e.g. risk analysis & operations procedure design)
          2. descriptive as deviation from normative (e.g., heuristics & biases)
          3. descriptive in terms of behavior traces (e.g., natural decision making)
    - high reliability explained by:
        * high degree of learning & self-org
        * facilitated by rapid turn-over of staff in navy
        * high degree of functional redundancy
    - desire to ensure organisational learning at all levels
    - error can only be found if standard of judgment exist
    - depends on perspective and reference for judgement chosen
    - causal trees do not include effect of compensating adaption of the people involved
    - human adaptation frequently compensates for attempts to improve system
      safety
    - performance controlled by perception of dynamic control characteristics
      of the interaction, not 'risk'
    - safety in the direct interaction with the work environment must be based
      on the identification of the boundary of safe performance by analysis of
      the work system, and criteria that drive continuous adaptive modification
      of behavior
    - efforts for improvment: control of performance in interaction with
      boundary, not on control of errors
    - difficulties in performing reliable diagnosis during disturbances also
      contributes to accidents
    - most recent major accidents appear cause by operation of systems outside
      predicted preconditions for safe operation during critical periods with
      excessive pressure from a competitive environment
    - important research issue: adaptive behavior of organiztaions under
      presure
11. Conclusion
    - specific research issues:
        * taxonomy of hazard sources & their control requirements
        * vertical interaction among decision makers at all levels of scoeity
          as it is found for various hazard domains
        * influence from naturalistic decision making modes on their responses to
          change and to competitive pressure


### A theory of shared understanding for software organizations
Jorge Aranda,
PhD dissertation,
Department of Computer Science
University of Toronto,
2010
[pdf][aranda10]

Aranda proposes *shared understanding* as a theory to explain challenges to
effective coordination and communication in software engineering organizations.

His theory is outlined in Chapter 5 of the dissertation. A summary of his model
can be found in figure 5.3 on page 101:

Coordination and communication consist of developing and negotiating a shared
understanding of:

* goals: What participants wish to achieve as a result of the situation
* plans: The set of decisions and actions to be taken to address the situation
* status: The current characteristics of the elements of the situation
* context: The current characteristics of surrounding elements that may have a
  bearing on the situation

His model consists of four attributs of interaction that can impact shared understanding:

* Synchrony: synchronous coordination/communication is more effective than asynchronous (async is harder)
* Proximity: co-located is more effective than distributed (distributed is harder)
* Proportionality: more effective when responsibility is proportiaional to authority (top-down is harder)
* Maturity: established patterns of coordination/communication are more effective than novel ones (novel is harder)

#### Synchrony

Understanding that is shared *synchronously* to the situation in which it applies is more effective than
an understanding about multiple potential situations shared asynchronously, in advance.

#### Proximity

Developing a shared understanding is most effective when it occurs in physical proximity to its situation.
One implication is that co-located orgs will be more effective in shared understanding than distributed ones.

#### Proportionality

Proportionality refres to a balance between the involvement of each agent in
the situation and the situation's needs; an alignment of responsibility with authority.

Proportionate coordination consists of coordination that is performed by the
people who will be primarily affected by the consequences—and most knowledge
about the details—of the situation they face. It emphasizes shared responsibility and team ownership
of the strategies used to deal with the production of their systems.

Disproportionate coordination is performed by people unrelated to the situation
under consideration. It is an imposition of a plan of action and of the goals to pursue in the
situation, determined by somebody other than those involved in it or by a more fraction of those involved.

When high-level coordination is disproportionate, the goals of some members of
the organization may be overlooked or dismissed.  Under some circumstances this
may lead to the successful completion of the software project from the point of
view of those doing the coordination, but thes ame project may have been a
failure from the point of view of those organization members that did not have
a say in goal-setting and planning.

### Maturity

Participants share their understanding taking advantage of their previous
patterns of behaviour.

As an organization evolves its behavior to face some particular kinds of
situations, the difficult of establishing a shared understanding of those kinds
of situations decreases considerably.

Hence, under many situations, the advantages of switching to a promising set of
coordination and communication patterns has to be weighted against the loss in
maturity entailed by engaging in a novel set of patterns.


[gray85]: http://www.hpl.hp.com/techreports/tandem/TR-85.7.pdf
[armstrong03]: http://www.erlang.org/download/armstrong_thesis_2003.pdf
[hamilton07]: https://www.usenix.org/legacy/event/lisa07/tech/full_papers/hamilton/hamilton_html/
[yuan14]: https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf
[hodges13]: http://www.somethingsimilar.com/2013/01/14/notes-on-distributed-systems-for-young-bloods/
[hodges13-talk]: https://www.youtube.com/watch?v=BKqgGpAOv1w
[allspaw12]: http://queue.acm.org/detail.cfm?id=2353017
[duffy16]: http://joeduffyblog.com/2016/02/07/the-error-model/
[leveson04]: http://sunnyday.mit.edu/accidents/safetyscience-single.pdf
[oppenheimer03]: http://roc.cs.berkeley.edu/papers/usits03.pdf
[besnard14]: https://hal-mines-paristech.archives-ouvertes.fr/hal-00720270
[lampson83]: https://www.microsoft.com/en-us/research/publication/hints-for-computer-system-design/
[saltzer84]: http://web.mit.edu/Saltzer/www/publications/endtoend/endtoend.pdf
[gainsburg07]: https://www.jstor.org/stable/30034962 
[alquraan18]: https://www.usenix.org/system/files/osdi18-alquraan.pdf
[perry12]: https://doi.org/10.1007/s10111-011-0207-2
[rasmussen97]: https://doi.org/10.1016/S0925-7535(97)00052-0
[aranda10]: http://www.cs.toronto.edu/~jaranda/pubs/ArandaGarcia_Jorge_201011_PhD_thesis.pdf
