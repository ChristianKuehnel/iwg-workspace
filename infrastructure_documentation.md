# Documentation of the project infrastructure

The set of tools used by the LLVM project are it's *infrastructure*. This page
contains an overivew of the existing tools, what they are used for and a contact
for each of these.

The [Getting Involved](http://llvm.org/docs/GettingInvolved.html) page
explains the intended workflows for using these tools.

## Communication

There are several tools used for communication.

### IRC

- see [IRC](https://llvm.org/docs/GettingInvolved.html#irc) on accessing
- no LLVM specific infrastructure required
- no central admin
- use case: interactive chats between community members
  - somewhat redundant to Slack and Discord
- integrations:
  - see [IRC](https://llvm.org/docs/GettingInvolved.html#irc)
- Ideas:
  - Do we have an integration with Discord?
- Current challenges:
  - N/A

## Mailing lists

- see [Mailing Lists](https://llvm.org/docs/GettingInvolved.html#mailing-lists>)
- Dedicated [Mailman](http://www.gnu.org/software/mailman/index.html) instance
- hosted at TODO
- administrated by TODO
- use cases: asynchronus communication of the community and code reviews
  - somewhat redundant to Discourse
- ideas:
  - Maybe integrate with Discourse?
- Current challenges:
  - Difficult to realize GDPR deletion requests

## Discourse

- [llvm.discourse.group/](https://llvm.discourse.group/)
- hosted service
- `Admins <https://llvm.discourse.group/about>`_
- use case: asynchronus communication of the community
  - somewhat redundant to the mailing lists.
- Integrations:
  - Github for single sign on

## Discord

- TODO: add URL and instructions for joning
- use case: interactive chats between community members
  - somewhat redundant to Slack and IRC
- TODO: do we have an integration with IRC?

## Slack

- [llvm.slack.com](https://llvm.slack.com)
- hosted service
- administrated by TODO
- use case: interactive chats between board and ops team
  - somewhat redundant to IRC and Discord

## Source Code Repository

- Multiple repositories hosted on [GitHub](http://github.com/llvm/)
  - most prominent: the [LLVM Monorepo](https://github.com/llvm/llvm-project)
- Hosted service by GitHub
- administrated by TODO
- use case: storing/versioning of the project source code
- Integrations:
  - display buildbot status
  - Email notifications

## Code reviews

- Code reviews for `llvm-project` and some other projects are performed in
  [Phabricator](https://reviews.llvm.org/) and on the mailing lists.
  - Some other projects are using GitHub PullRequests.
- Phabricator is hosted on Google Cloud
- Administrated by TODO
- Integrations:
  - Single sign on with Google and Github
  - Reading data from Github
  - Triggering builds on pre-merge testing
  - sending Emails on mailing list

## Build infrastructure

The project is using multipe build systems with different scopes and
technologies.

### Build bots

- use case: post-merge testing on various operating systems and platforms
- workers hosted and maintained by the community
- server hosted and maintained by Access Softtek
- [Production server](http://lab.llvm.org:8011/), sending emails
- [Staging server](http://lab.llvm.org:8014/), no email notifications, for
  testing purposes.

### Green dragon

- [green.lab.llvm.org/green/](http://green.lab.llvm.org/green/)
- use case: post merge testing on Apple's MacOS
- Hosted at Apple
- administrated by TODO

### Pre-merge testing

- use case: pre-merge testing of patches on Phabricator
- TODO: link to github page
- Integrations
  - Phabricator to get patches and show results
  - Github repository to get sources
  - Buildkite to run the builds

### LLVM GN buildbot

- [45.33.8.238](http://45.33.8.238/)
- use case: post-merge testing using GN build system
- Hosted at TODO
- Administrated by TODO

### LNT

- [lnt.llvm.org](http://lnt.llvm.org)
- Nightly tests, measuring performance and code size
- Current challenges:
  - is looking for new maintianer

## Bug Tracker

- [bugs.llvm.org](https://bugs.llvm.org/)
- self-hosted Bugzilla on TODO
- Administrated by TODO
- Migration to Github Issues in progress

## Build Systems

- The official build system is *CMake*.
- other, unsopported build systems:
  - [gn](https://github.com/llvm/llvm-project/tree/master/llvm/utils/gn)
  - Support for bazel currently in discussion.

## Test tooling

### Unit testing

- using google test

### LIT

- home-grown testing framework

## Web sites

- llvm.org
- foundation.llvm.org

## Content Delivery Network (CDN)

- TODO
