# BuildBots as a service

* Proposal: TODO
* Author(s): @ChristianKuehnel
* Review Managers: TBD1, TBD2[, TBD3, TBD4]
* Status: WIP

<!--_During the review process, add the following fields as needed:_ 

* Pitch Thread: [1](url for discussion) [2](url for discussion)
* Decision Notes: Rationale, Additional Commentary
* Previous Revision: [1](url for previous significant revision)
* Previous Proposal: LP-0012

-->

## Introduction

We propose to introduce a paid-for continuous integration (CI) service. The
service shall set up and maintain critical CI infrastructure for the LLVM
project.

The community shall decide on a set of critical configurations that shell be
covered by this service. The service shall be paid for by the LLVM foundation
based on donations from sponsors.

The goal is to improve the quality of service of our CI infrastructure,
specifically to shorten the response times, increase stability of the main
branch and reduce the false-positive ration of build failure notifications.

<!--
This proposal was discussed in this [pitch thread](URL for the pitch thread on llvm-dev).
-->

## Motivation

Today, the BuildBot master is maintained by Access Softek on behalf of and paid
for by the LLVM foundation. The workers are donated and maintained by different
community members. Workers and builders are configured as every owner sees fit.
There is no planned coverage of the various sub-projects, hardware platforms
or build configurations.

People also have been complaining recently about an increasing number of false
negatives in the email notifications due to failing workers.

## Proposed solution

The Infrastructure WOrking Groups shall establish and monitor a buildbot
operations service:

1. Survey the community to identify the most critical
    * hardware platforms
    * CMake options
    * sub-projects
    * operating systems
    * ...?
2. Based on the survey, the IWG will propose a minimal set of workers and
  builders to cover these configurations and estimate the hardware and financial
  requirements for these.
  The IWG will also propose SLOs for the entire service.
  This proposal shall go through a community decision process.
3. The LLVM foundation will negotiate with their sponsors to find ways to cover
  these requirements via donations. Sponsors will have some influence on the
  selected configuration to ensure their needs are covered.
4. The IWG will start an RFP for a maintainer. The maintainer would be paid for
   by the LLVM foundation. The maintainers work shall include:
    * Maintain the BuildBot server.
    * Rent/buy, set up and maintain the builders and workers.
    * Update the configurations if the community requirements change.
    * Guarantee the SLOs (false-negative rate, uptime, build performance, ...)
    * Help community members set up and maintain additional non-critical
      configurations.
    * Monitor the SLOs for community-operated workers and take them offline as
      needed.
5. The LLVM foundation will then hire a contractor.
6. The IWG will manage the work of the contractor and monitor the SLOs.
   Twice a year the IWG will discuss with the community if changes to the
   workers or builders are needed and wi

## Impact On Other Projects

None, this is only an optimization of our CI infrastructure and it's operations.

## Frequently Asked Questions

**Where does the hardware come from?**

Whenever possible the hardware would be rented from some cloud providers. Only
if we have critical configurations not available there, we would have to
look into server hosting.

**What about non-critical configurations?**

No change there, community members are free to set up whatever configuration
they want. However the maintainer will enforce some SLOs to reduce the
false-positive rate for build failure notifications.

**Do we need to change the maintainer of the server?**

Wo be able to guarantee the SLOs, the maintainer shall be responsible for
the server and the workers. However if the current maintainer wants to
participate in the RFP, they are welcome to do so.

## Alternatives considered

None, at this point.
