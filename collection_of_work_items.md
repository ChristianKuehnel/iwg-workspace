# Ideas for initial work items

This is an unsorted, unprioritized list of ideas the working group could look
into. Once we have set up some task management tool (probably GitHub Issues)
this list shall be migrated there, so we can discuss these one-by-one.

* Run a survey in the community to understand the largest pain points and
  prioritze potential improvements.
* Create and maintain a public documentation of the existing infrastructure and
  the supported workflows (what, why, who), including down-stream usages of
  LLVM.
* Define and agree a vision for LLVM infrastructure and for the design
  principles thereof: What should the development workflow and the
  infrastructure look like?
* Identify the need for addons for Github the community is missing right now
  (e.g. subscribing to labels on Github Issues).
* Help the community come to a decision on using Phabricator vs. GitHub Pull
  Requests for code reviews, then implement the change.
* Create a roadmap for the handover of the existing infrastructure to a
  contractor. We need to review each one and decide if it makes sense
  to take them over as they are, drop them, or replace them with something else.
  A list of services where the respective maintainer would like to hand over
  the maintainance work to the LLVM foundation:
  * Phabricator (in case we stay with it)
  * Pre-merge testing
  * Buildbot workers
  * clangd remote index for LLVM
  * [LNT service](http://lnt.llvm.org/)
  * ...
* Create new design and structure for the LLVM website, migrate the existing
  content there.
* Create a test strategy for the LLVM project and refactor the existing build
  infrastructure to meet the new test strategy. Some ideas:
  * Extend/improve pre-merge testing: reduce false-positives, have better
    integration with post-merge testing, cover more configurations, improve
    performance, ...
  * Multi-stage CI: run “cheap” builds first, run “expensive” builds only on
    commits where the cheap builds have passed.
  * Set up a collector dashboard showing build results for all CI systems per
    commit, e.g. Treeherder or something GitHub based.
  * Investigate if we can get a good deal from GitHub Actions with sponsored
    hardware, similar to
    [Rust](https://blog.rust-lang.org/inside-rust/2020/07/23/rust-ci-is-moving-to-github-actions.html).
  * Create a plan of the "important" buildbot configuration we need in order to
    detect the bugs with large impact (contributors and downstream). Then have
    one central team/contractor operate these to ensure consistency and quality.
  * Introduce a `green` branch in git, merge the `main` branch whenever a set of
    CI checks passes on `main`. So `green` is only a few commits behind `main`,
    no direct pushes, not cherry-picking. This branch cen be used for cases
    where people prefere stability over the latest version.
* Gather user feedback on the existing infrastructure: Where are the pain
  points? What would our community like to see improved?
* Migration of all python scripts and tools to Python 3 as Python 2 is
  deprecated (already in progress).
* Reach out to downstream infrastructure teams (e.g. Rust, Tensorflow) and
  understand if we have infrastructure topics we want to cooperate on.
* Define Service Level Objectives (SLO) for our infrastructure and monitor
  them. Set up monitoring and altering for our infrastructure.  Derive measure
  where we do not meet our SLOs.
* Migrate Windows setup instructions off GnuWin32 as it’s deprecated and add
  installation instructions users can copy-and-paste into their shell.
* Investigate the Rust project infrastructure and see what would be helpful to
  LLVM. Some examples:
  * Create a benchmark tool to compare the performance of the compiler and the
    compiled code across versions, there is also a project for that.
  * Set up some central source of truth for managing user accounts, group
    membership and user/group permissions. Then configure all tools
    accordingly.
* Investigate if/where we need to have Terms of Service and Pricacy Agreements.
* Figure out where we need to be able to handle GDPR-related requests and
  how that could be done.
* Decide what to do with the mailing lists and GDPR deletion requests.
* Decide if we want to have mandatory pre-merge testing and what it should
  look like.
* Migrate bug tracker to GitHub issues (already in progress).
* Figure out, where we could use more/better documentation or traning material
  (e.g. tutorials, videos).
* Roll out clang-tidy and clang-format for new/modified code to all repositories. 
  * Configure rules for the projects.
  * Set up pre-merge and post-merge checks to find (new) voilations.
  * Set up dashboard and metrics to visualize improvements over time.
  * Maybe also do a one-shot re-formatting of theentire codebase.
* Create (moderated) blog for communication within and beyond the community:
  Announcement of news, stories from users, success stories, ...
