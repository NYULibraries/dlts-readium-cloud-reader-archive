DLTS Readium `cloud-reader/` archive
====================================

ReadiumJS viewer builds are not 100% reproducible due to the lack of locking
mechanism for the NPM module dependencies.  We do have a build system for making a
reproducible `cloud-reader/`: [dlts-readium-js-viewer](https://github.com/NYULibraries/dlts-readium-js-viewer).
However, the build system relies upon snapshots of the exact `readium-js-viewer` repo,
and even at maximum compression these take up a lot of space.  Currently we are
only keeping snapshots for the latest production build and any versions we
happen to be working on currently.  This means that we can never reliably run
a re-build for an old version again.  Realistically, we would only need
to do this if we wanted to re-build an older Readium with a new new version of
our plugin, and the chances of that seem unlikely.

For rollback purposes, we are archiving our past `cloud-reader/` distributions
in this repo.  The loose naming scheme is "cloud-reader-[YYYY-MM-DD]" where the
date is the day the reader was deployed in production.  Note that the first
`cloud-reader/` we ever deployed in November 2015 is not saved here as we
never kept a copy of it.

These archived versions can be dropped in as is.



