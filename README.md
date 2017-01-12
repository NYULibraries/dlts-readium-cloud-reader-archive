DLTS Readium `cloud-reader/` archive
====================================

ReadiumJS viewer `npm run dist` builds are not 100% reproducible due to the lack of locking
mechanism for the NPM module dependencies.  We have a build system for making a
reproducible `cloud-reader/`: [dlts-readium-js-viewer](https://github.com/NYULibraries/dlts-readium-js-viewer).
Originally, the build system relied upon snapshots of the exact `readium-js-viewer` repo,
and even at maximum compression these took up a lot of space.  The plan was to
only keep snapshots for the latest production build and any versions we
happen to be working on currently.  This meant that we could never reliably run
a re-build for an old version again.  Realistically, we only need
to do this if we want to re-build an older Readium with a new new version of
our plugin, and the chances of that seem unlikely.  For rollback purposes,
we were archiving our past `cloud-reader/` distributions in this repo.

Since then, the [yarn package manager](https://yarnpkg.com/) was released,
and we were able to update our builder to use yarn for dependency locking.
Starting from cloud-reader version 2017-01-12, all past versions can
be reliably rebuilt without snapshots, so there isn't really a need
to archive backup copies of cloud-readers/.  For now will just continue
to do it.  It might prove convenient.

The loose naming scheme is "cloud-reader-[YYYY-MM-DD]" where the
date is the day the reader was deployed in production.  Note that the first
`cloud-reader/` we ever deployed in November 2015 is not saved here as we
never kept a copy of it.

These archived versions can be dropped in as is.



