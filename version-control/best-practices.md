Maintaining a Repo
---------------

* Avoid including files in source control that are specific to your
  development machine or process.
* Delete local and remote feature branches after merging.
* Perform work in a feature branch.
* Rebase frequently to incorporate upstream changes.
* Use a pull request for code reviews.

Write a Feature
---------------

Create a local feature branch based off develop.

    git checkout develop
    git pull
    git checkout -b <branch-name>

Rebase frequently to incorporate upstream changes.

    git fetch origin
    git rebase origin/develop

Resolve conflicts. When feature is complete and tests pass, stage the changes.

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

[good commit message]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html

Review Code
-----------

A team member other than the author reviews the pull request.


When satisfied with the PR, they comment or indicate `Ready to merge.`

Merge
-----

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
