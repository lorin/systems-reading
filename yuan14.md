# Simple Testing Can Prevent Most Critical Failures: An Analysis of Production Failures in Distributed Data-Intensive Systems

Ding Yuan, Yu Luo, Xin Zhuang, Guilherme Renna Rodrigues, Xu Zhao, Yongle
Zhang, Pranay U. Jain, and Michael Stumm
Proceedings of the 11th USENIX Symposium on Operating  Systems Design and Implementation (OSDI '14)
Oct. 2014.

* [pdf]
* [video]
* [slides]

Terminology:
* Catastrophic: affects all or a majority of users

## Slides

### Key findings

* Failures are the results of complex sequence of events
* Catastrophic failures are caused by incorrect error handling
    * Many are caused by a small set of trivial bug patterns
* Aspirator: a simple rule-based static checker
    * Found 143 confirmed new bugs and bad practices



## Paper

Most failures require multiple events to trigger. Need stress testing plus other
techniques such as fault injection.

Order also matters.


### Findings

1. A majority (77%) of failures require more than one input event to manifest, but most of the failures (90%) require no more than 3.
2. The specific order of events is important in 88% of the failures that require multiple input events.
3. Almost all (98%) of the failures are guaranteed to manifest on more than
   than 3 nodes. 84% will manifest on no more than 2 nodes
4. 74% of failures are deterministic
5. 53% of deterministic failures have timing constraints only on the input
   events.
6. 76% of the failures print explicit failure-related error messages
7. For a majority (84%) of the failures, all of their triggering events are logged.
8. Logs are noisy: the median of the number of log messages printed by each failure is 824.
9. A majority of the production failures (77%) can be reproduced by a unit test.
10. Almost all catastrophic failures (92%) are the result of incorrect handling of non-fatal errors explicitly signaled in software
11. 35% of the catastrophic failures are caused by trivial mistakes in error
    handling logic -- ones that simply violate best programming practices;
    and that can be detected without specific knowledge.
12. In 23% of catastrophic failures, incorrect error handling would have been exposed by 100% statement coverage testing on the error handling logic.


## Categories

- Complexity of failures (most aren't *that* complex)
- Role of timing (often deterministic enough that they could be reproduced in a test)
- Logs enable diagnosis opportunities (logs are good, but noisy)
- Failure reproducibility (these are catchaable in tests if we know where to look)
- Catastrophic failures
    - Trivial mistake in error handlers
    - System-specific bugs


## Opportunities for improved testing

- Starting up services: more than half of the failures require the start of some services
- Unreachable nodes: 24% failures occur because a node is unreachable
- Configuration changes: 23% of failures are caused be config changes.
    - 30% of these involve misconfigurations
    - Remaining majority involve valid changes to enable certain features that may be rarely-used
- Adding a node: 15% of failures are triggered by adding a node

## Limitations

1. Representativeness of the selected systems
1. Representativeness of the selected failures
1. Size of our sample set
1. Possible observer errors

## Conclusions

- We should be able to catch most of these issues in unit testing
- Logs are useful but noisy
- We should put more effort into writing the error-handling code

### Changing how we code

### Changing how we test

- Daniel Jackson's "Small Scope Hypothesis": most bugs have small counterexamples
- Most failure can be reproduced with unit tests



[pdf]: https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf
[video]: https://www.usenix.org/conference/osdi14/technical-sessions/presentation/yuan
[slides]: https://www.usenix.org/sites/default/files/conference/protected-files/osdi14_slides_yuan-ding.pdf
