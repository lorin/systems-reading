# Systems and failure reading list

This page contains references to books and papers about complex systems and how
they fail. I'm interested in how these relate to software systems, so my
comments will be biased in that direction. In particular, the
[availability](#availability) section is specific to high availability
in distributed systems.

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


### Risk management in a dynamic society: a modelling problem
Jens Rasmussen,
Safety Science Vol. 27, No. 2/3, pp. 183-217, 1997

<https://doi.org/10.1016/S0925-7535(97)00052-0>

Rasmussen advocates for a systems-based approach to thinking about how
accidents occur. He argues that accidents occur because the system migrates
across a dangerous boundary, and this migration occurs during the course of
normal work.

#### Terms
- Systems approach
- Control-theoretic
- decisions, acts, and errors
- hazard source
- anatomy of accidents
- energy
- systems thinking

#### Sentences

- Attempts to improve the safety of a system from models of lacal features were
  compensated by people adapting to the change in an unpredicted way
- It is thus becoming increasingly difficult to model systems in isolation and
  to make small-scale, local experiments to evaluate modles
- competitive environment
- They cannot, however, foresee all local contingencies of the work context
- operators' violations of oformal rules appear to be quite rational
- behaviour is context dependent
- commerical success in a competitive environment implies exploitation of the
  benefit from operating at the fringes of the usual, accepted practice
- accidentals caused by a systemic migration of organizational behaviour toward accident under the
  influence of pressure toward cost-effectiveness in an aggressive, competitive
  environment
- competitive stress
- a systemic migration toward the boundary of functionally acceptable
  performance and, if crossing the boundary is irreversible, an error of an
  accident may occur
- it is often concluded by accident investigations that the particular accident
  was actually waiting for its release
- The important issue is that the stage for an accidental course of events very
  likely is prepared through time by the normal effeorts of many actors in
  their resective daily work context, responding to the standing request to be
  cost-effective (normal work).
- an explanation of the accident in terms of events, acts, and errors is not
  very useful for design of improved systems.
- new appraoch to representation of system behavior should focus on mechanisms generating behaviour in the acutal, dynamic work context
- instead of fighting deviations, should make the boundaries explicit and known
- develop coping skills at the boundaries
- An empiricial struggle for a good 'safety culture' will never end because it only works as long as it acts as a continuous pressure compensating the functional pressure of the work environment.
- The most promising general approach to improved risk management appears to be
  an explicit identification of the boundaries of safe operation together with
  efforts to make these boundaries visible to the actors and to give them an
  opportunity to learn to cope with the boundaries.
- accidents are created by the interaction of potential side effects of hte
  performance of several decision makers during their normal work.
- performance crtieria in actual work are often implicit and difficult to make
  explicit
- A detailed study of the control requirements of the dominant hazard sources
  of a work system is therefore mandatory for risk management.
- In environments where accidents are frequent and small-scale, safety is typically controlled empirically from epidemiological studies of
  past accidents
- high reliability explained by high degree of learning & self-organization,
  faciliated by rapid turn-over of staff in the navy
- very high degree of functional redundancy, protecting against errors and resource violations
- risk homeostatis - adaption seeking to maintain a stable level of perceived
  risk
-  most recent major accidents in large scale industrial systems appear to be
   caused by operation of the systems outside the predicted preconditions for
   safe operation during critical periods with excessive pressure from a
   competitive environment

#### Outline

1. Introduction
2. The problem space: risk management in a dynamic society
3. The present dynamic society
4. Modelling by structural decomposition: tasks, acts and errors
5. Accident causation
6. Modelling by functional abstraction: migration toward the boundary
7. Control of system performance
8. Risk management: a control task
    1. Identification of controllers
    2. Work objectives
    3. Information on actual state of affairs
    4. Capability and competence
    5. Commitment
9. Identification of constraints and safe boundaries
10. Present trends in the paradigms of human sciences
    1. Decision research
        1. Normative models
        2. Descriptive models in terms of deviation from normative behavior
        3. Descriptive models of actual behavior
    2. Organizational theory
        1. Normative theories
        2. Models in terms of deviation from normative behavior
        3. Models in terms of features shaping organisational behavior
    3. Occupational safety research
        1. Models in terms of normative practice
        2. Models of behaviour in terms of normative performance and errors
    4. Major accident research
        1. Normative taks models and work instructions
        2. Models in terms of deviations from normative performance
        3. Models in terms of actual behavior of individuals and organizations
    5. Implications for research and for control of human behavior
11. Conclusion

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

Revision: Accident investigation is a social process, where causes aer
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

# End-to-end Arguments in Systems Design
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
