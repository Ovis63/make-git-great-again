# **Make Git Great Again** - _Building a better history than the 45th President of the USA_

Git is a fantastic tool but there's a lot more to it than just the stage and commits. It's important to have a good grasp of some of the basics. We're going to work through a few basics which you might not have been taught.

We'll look at: the stash, branches, merging, and pull requests in this workshop.

## The stash

> Use `git stash` when you want to record the current state of the working directory and the index, but want to go back to a clean working directory. The command saves your local modifications away and reverts the working directory to match the `HEAD` commit.
- [Git man-pages | Stash](https://git-scm.com/docs/git-stash)

### Use cases:

* You've got some changes you're part way through but you need to quickly check a build of the source on `HEAD`, perhaps to see if you've introduced a bug accidentally.
* You think you've gone wrong with your approach and want to quickly try a new approach which you might ditch in favour of your current changes.

**Note** do not use the stash as a replacement for the reflog, a stash is only local and thus very easy to loss if a hard drive breaks for example.

## Branches and merging/rebasing

Branches are potentially one of the most powerful and core aspects to Git. If you understand branches properly, many other features will make a lot more sense.

Branching exists to allow you to diverge your history away from a particular point in two different ways. Most version control systems allow this, git however makes branching a **first class citizen**!

Merging is the act of pulling changes from one branch into your current branch. Rebasing is an alternative to merging which is often favoured but the idea is more complex and not one we'll explore here.

### Use cases:

* You wish to implement a new feature which will take multiple commits to get to a full working state. Create a branch from `master` for your new feature and `git merge` it in later. (GitHub Flow)
* You want to fix a bug or experiment with a change before bringing it into the `master branch`. (GitHub Flow)
* You wish to isolate a release candidate to ensure you only apply minor bug fixes but can continue major feature development (Git Flow)

## GitHub Flow

A workflow for using git and GitHub which aligns with general open source contribution processes.

* `master` is **always** deployable. Perhaps that's to a client or end users.
* Want to make a change to the code base? Branch from the `HEAD` of `master`, name the branch sensibly.
* Make atomic commits to the branch.
* Request a pull of `my-feature` into `master` (pull request) as soon as the changes are ready to have eyes on them.
* Have the code reviewed, discussed, and make any required changes (iterate on it).
* When everything is finished and reviewed, accept the pull request and merge the branch into master.

### Use cases

* Literally any project.
