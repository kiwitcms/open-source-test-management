# What is this

Multiple open source projects have come to us and said
**We like Kiwi TCMS and we need a system like that but we have no idea
how to get started**. The reality is that the majority of these projects
rely on contributors and most of them would prefer to be developers and
to contribute code! Testing regularly remains on the side.

This repository contains guidelines for organizing testing and is targeted
primarily towards other open source projects. We'll try to keep it brief
and actionable so you can get started immediately.

**Notes:**

- The word "testing" is overloaded with meaning in our industry. Sometimes it
  means checking something, other times if means to verify, yet other times
  it means to experiment. Here it is used as a catch-all term so you will have
  to be aware of the context in which you want to apply these guidelines!


# Evaluate your risk areas

Testing is a process for collecting information and filling a knowledge gap
that we have, see
[this illustration](https://raw.githubusercontent.com/atodorov/qa-automation-ruby-101/master/module00/testing_knowledge_gap.png).
In the general case of an established software project we should start
with an evaluation and find out which areas pose more risk than others:

- Could be UI
- Could be translations
- Could be installation
- Could be specific set of functionality

To quickly start evaluating these areas:

- Talk to your users & developers - they always know specific things
  which tend not to work often
- Read through your bug tracker, check all reports for the last few versions
- Talk to support/forum admins - when there are problems
  people tend to ask about them

When you start digging in the above resources you will start noticing patterns.
Regressions in bug fixes and functionality will be immediately obvious. Questions
around a common area of misunderstanding or common root cause as well.

**Notice:** Risk here is very loosely defined as
**if it goes wrong it's bad for the project/community**! It is up to you,
the tester, to assign categories and priorities and evaluate how much the
software project can tolerate for every specific area. For example a cumbersome
installation will be a deal breaker for a desktop software but for a web app
which would mostly be consumed as-a-service may not be.


# You need test cases

Armed with your list of risky areas you need to understand why these things
happen which will hint at how they can be prevented in the future.
Mind that not everything needs an automated check or even a manual scenario. Some
items can be better resolved at the development process - e.g. more tooling, customized
IDE/linter plugins, etc.

For the items that remain you need to describe them in details. Be specific.
From a common user story there could be multiple scenarios, both positive and
negative ones. Use whatever language will work best for your community -
could be Given-When-Then, could be 1, 2, 3, could be example data, etc. The point
is that whomever will be looking at this scenario (with the intention to later execute it)
understands what the author means. Generally testers will tell you that ambiguity
is not desired however variations in how different people understand and execute the
steps to reproduce will reveal different paths, e.g. more scenarios.

Usually in testing & QA we organize the test cases that we have in test plans
or test suites, e.g. "Installation testing", "Localization testing",
"Performance testing", etc. The division isn't that important, the important
thing is that you have a plan what needs to be done and where to focus your effort!


# You need a process

Software testing/Quality Assistance (it's not really assurance anymore these days)
is equal parts tools & technology, documentation and process. Be simple:

- When would certain testing activities be executed - daily, weekly, on every pull request
  or you will work from pre release branches
- How much time is needed for various testing/stabilization and other pre-release
  activities
- Are you going to gate changes going into certain branches (e.g. string freeze,
  feature freeze, bug-fixes only) or not
- Who will be responsible for all of the above and how will they communicate? You
  don't want to turn this into blaming game but everyone needs to know where & how
  testing fits
- What about the community, how are they going to be engaged? Do you need full-time
  contributors or part-time, etc. What level of access & knowledge is required from them


# Engage your community

You want to have test executions against various builds and work towards
an increasing number of PASSing results.

A fairly tipical process would be to have a small dedicated team who is responsible
for evaluating risk, documenting test plans & test cases, overseeing the process(es)
and a larger pool of volunteers who will help with test execution.

Organizing test days per area would be a good way to go. Call to action for verifying
that bugs have indeed been fixed before a release is also good. Some contributors
would be happy to explore the cutting edge nightly builds and give you regular feedback.

The frequency of test execution for each test plan varies:

- Translation - probably once shortly before relase when you see you have 100% of
  the desired languages. Then check for typos, language style, etc.
- Main functionality - rather often, probably on nightly builds or weekly
- Performance, specialized areas - one-two times per release probably, especially if
  these aren't critical and/or do not change often


# Using a TCMS

- First you need to have a testing process and then infrastructure, not the other way
  around
- You don't need Kiwi TCMS or any other system to organize all of the above
- A TCMS system is used just to keep track of what has been done so that in the future
  you can go back to it, examine it and decide if you need to do something else


# Rinse & repeat

This is an iterative process. Design it like that from the start.
Set aside a regular period in which you will be evaluating your testing process(es)
and tweaking them as needed.


# References

*Please consider contributing a file/URL describing the testing process within
your own ogranization!*


# What about the name

It is a tribute to the *Open Source Test Management* stand at FOSDEM
started by SystemTestPortal and Kiwi TCMS in 2019.

!["Picture from FOSDEM"](https://raw.githubusercontent.com/kiwitcms/open-source-test-management/master/open-source-test-management-fosdem.jpg)
