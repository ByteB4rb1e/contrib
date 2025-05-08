# Hello future self

In case you've been obducted, went to prison, with no access to the internet for
a long time, or started suffering from dementia - this is a quick explainer on
what this is.

You use this repository to organize your contributions you are making on GitHub.
You've started doing this on the 9th of May 2025.

This repository itself is another submodule of your
[workspace](https://bitbucket.org/byteb4rb1e/my-workspace/src/master/), where
you will find more info on where to get your GPG and SSH keys back. In case your
workspace no longer exists, you have two physical encrypted backups of everything in
places you hopefully can recollect in addition to the password and key. You also
have backups in Proton Drive.

# Getting started

It is a simple concept. For any contribution you make, you have to create a fork
of the original repository anyway. You are doing so only if you have an issue
id, which serves as the basis for creating a pull request.

> TODO: You wanted to do simple offline issue tracking, but you were hesitant as
> you didn't quite have a concept yet on how to seperate to-dos belonging to
> this repository from the issues you're tracking in GitHub. You do use a TODO
> issue tracker in other repositories of yours though...

When creating the fork, you only fork the main branch.

After you've created the fork, you clone the fork as a submodule into this
repository under `ongoing/<organization-id>/<repo-slug>`.

Then you add a new remote, ideally call it `parent` and let its URL point to the
repository you are creating a PR for. This you use for rebasing your working
branch.

Then, you create a working branch. If it is a bugfix you are contributing, the branch will be named
`bugfix/<issue-id>`. If it is a feature you are contributing, the branch will be
named `feature/<issue-id>`.

Make sure to commit the working branch of the submodule to this repository.

Then delete the main branch locally, as well as in your fork and set the default
branch in GitHub to point to your working branch.

# Concluding

No matter if your contribution was rejected, or accepted, after you have no more
coding to do, you create a patch in comparison to the `parent` remote's main
branch and store it under
`archived/<organization-id>/<repo-slug>/<issue-id>.patch`.

Assuming you're on the working branch, you've actually named the remote `parent`
and their main branch is called `main`:

```
git format-patch parent/main --stdout > archived/<organization-id>/<repo-slug>/<issue-id>.patch
```

Then remove the submodule from `ongoing/` and commit both changes.

That's all for now. Go easy on yourself.
