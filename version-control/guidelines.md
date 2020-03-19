# git

## Resources
Here are some useful links in learning about git:
http://git-scm.com/
http://gitvisual.com

## use git
CoLab uses git for all version-control purposes.

### Maintaining a Repo

* Avoid including files in source control that are specific to your
  development machine or process.
* Delete local and remote feature branches after merging.
* Perform work in a feature branch.
* Rebase frequently to incorporate upstream changes.
* Use a pull request for code reviews.

### Write a Feature

Create a local feature branch based off develop.

    git checkout develop
    git pull
    git checkout -b <branch-name>

Rebase frequently to incorporate upstream changes.

    git fetch origin
    git rebase origin/develop

Resolve conflicts. When feature is complete and tests pass,
stage the changes.

    git add --all

When you've staged the changes, commit them.

    git status
    git commit --verbose

Write a [good commit message]. Example format:

    Present-tense summary under 50 characters

    * More information about commit (under 72 characters).
    * More information about commit (under 72 characters).

    http://project.management-system.com/ticket/123

If you've created more than one commit, use `git rebase`
to squash them into cohesive commits with good messages:

    git rebase -i origin/develop

Share your branch.

    git push origin <branch-name>

Submit a pull request.

Ask for a code review.

[good commit message]: 
http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html

### Review Code

A team member other than the author reviews the pull request.

When satisfied with the PR, they comment or indicate `Ready to merge.`

### Guidelines for PR reviews:

* Actually Review
  * Don't just accept without reading the commit! :)

* Timeliness
  * More than likely, the person who wrote the PR is eagerly waiting for the go-ahead to merge. Don't make them wait too long!

* Honesty
  * It's good to think through things as soon as possible. You may think: "I'd do it differently, but I'm sure they have a good reason to do it this way." That might be true, but it might not. The author of the PR may like your idea better! Even for big / fundamental things: there's no such thing as a stupid question.

* Test
  * If practical to do so, actually testing out the PR can be highly beneficial. You might be able to catch something that the dev missed.

* Communication
  * PR Reviews should be held to the same high standards of communication we use everywhere else at CoLab. Be humble, be nice, communicate clearly and completely, be thoughtful, be positive.


### Merge

Rebase often. If you do not, you will diverge farther and farther from
origin. Fixing conflicts farther from origin is much more difficult
than fixing conflicts nearby origin.

Squash commits like "Fix whitespace" into one or a small number of
valuable commit(s). Edit commit messages to reveal intent. Run tests.

    git fetch origin
    git rebase -i origin/develop

Delete your remote feature branch.

    git push origin --delete <branch-name>

Delete your local feature branch.

    git branch --delete <branch-name>
