# Evidence based working

In our line of work, building software for P2P financial products, it is
extremely important that we operate in an evidence based manner.

Of course, proofs are even better than evidence, and we prefer those where we
can get them, but most of the time evidence is what we have to settle for.

## Automate the production of evidence

The number one reason for not producing evidence, is that it is often difficult
to produce reliably.

Automating the process of producing evidence has several benefits

- Distributes access to the evidence across the entire team
  - Reduces reliance on a single team member
    - They may not be available in your time zone or due to other responsibilities
    - They may misinterpret the evidence, that another member might correctly
      interpret if given the chance
- Increases the speed of evidence production
  - Consider manual software testing, automated example based testing, and fuzz
    testing. Each producing orders of magnitude more evidence in comparable time
    frames than the last.
- Standardises the evidence produced
  - It's very difficult to directly compare inconsistently collected evidence
    over a long period of time, undermining all the value produced

Examples of evidence automation include:

- Simple scripts that can be run on GitHub actions as needed
- Logging/monitoring inline in prod
- Test suites for code
- Back testing and models strategies from onchain data

## Establish a baseline before making large changes

We are typically biased towards assuming that when we undertake some large
project, the end result will be better than the current state of things.

Indeed, why would we ever start a large new project if we expect a worse final
outcome?

The problem, however, is often knowing when to stop, or at least to cut a 1.0
release.

Ideally we should release as early and often as possible, which would be as soon
as the new thing is at least as good as the old thing, with more room to grow.

To establish this in evidence, we need to define some KPIs/metrics that can be
measured equally in the old/new setup.

- Difficult to game/misinterpret
- Clear/simple implementation while covering as many edge cases as possible

And we actually need to do the work of establishing what the baseline is in the
old setup, ideally before we even consider releasing the new one.

Examples include:

- "All the tests pass" for a codebase refactor
- "Uptime and efficiency" for an arbitrage bot
- "Volume and TVL" for a DEX
- Etc.