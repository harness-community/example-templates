# Mono Repo Builder

This folder contains an example pipeline designed to show how you can build a set of apps in a mono repo, and run a stage after to perform any final build/deployment/cleanup actions needed.

This relies on a push trigger, included in the [trigger.yaml](trigger.yaml) file, which will trigger for commits created as a result of a PR merge in GitHub.  The pipeline uses the `<+trigger.changedFiles>` expression to get a list of changed app directories, iterate a stage across each directories, and run the post build actions stage once all builds are complete.