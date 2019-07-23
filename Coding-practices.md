# Coding practices

This document is a working draft.  Edits and comments welcome.

These practices apply to software that is “released” or in production, meaning software, produced by NeuroData team, that is used on a regular basis or is published on a software repository.

## Principles

1. Any code from NeuroData (eg, written based on work here, and therefore funded by our funders, rather than for fun), live in a neurodata controlled org, rather than a personal repo (much like if you worked at google or a startup).
2. Everything is always a PR, never a direct commit to master
3. People using the code should always use master, if you have some branch that you think is better than master for some reason, then it is your responsibility to make a PR to master, rather than encouraging other people to use some untested branch. that is, unless you want them to be testing for you, which is a different thing.


## Git Usage 
### Some good tips from [help.github.com](https://help.github.com/en/articles/removing-sensitive-data-from-a-repository)
> There are a few simple tricks to avoid committing things you don't want committed:

> * Use a visual program like GitHub Desktop or gitk to commit changes. Visual programs generally make it easier to see exactly which files will be added, deleted, and modified with each commit.
> * Avoid the catch-all commands `git add .` and `git commit -a` on the command line -- use `git add filename` and `git rm filename` to individually stage files, instead.
> * Use `git add --interactive` to individually review and stage changes within each file.
> * Use `git diff --cached` to review the changes that you have staged for commit. This is the exact diff that `git commit` will produce as long as you don't use the `-a` flag.

## Releases

* Use the NeuroData PyPi account when uploading to PyPi
   * Ask neurodata admin team for access
* Tag / create a github release on each release to CRAN/PyPi

## Master branch
* Github settings
* Restrict editing to users in teams with push access only 
* Add rules for master branch
    * Require pull request reviews before merging 
    * Include administrators 
    * Restrict who can push to master

## [Feature branches](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
* Create a branch for each feature addition
* Each PR should ideally encapsulate a single feature.  This allows reviews to be well contained
* Don’t let branches get stale (merge in changes from master frequently)
* Squash and merge each PR
* Keep the commit history clean and concise. Commit messages should be in [imperative mood](https://chris.beams.io/posts/git-commit/).

## Issues
* An Issue should consist of a manageable task with a concrete DOD; larger tasks should be split into multiple issues, with milestones, epics, and or tags.
* Create an issue template.  Can use [these](https://github.com/neurodata/rerf/tree/staging/.github/ISSUE_TEMPLATE) as a guide.

## Code formatting
* [Black](https://github.com/ambv/black) for Python
* [Styler](https://github.com/r-lib/styler) for R
* Automatically apply formatting before commit (either format on save or format on commit)

#### Consider the following naming conventions (Python)
* [PascalCase](http://wiki.c2.com/?PascalCase) for class names
* descriptive_names_with_underscores for function and variable names
* singlename.py for module names
* ALL_CAPS_WITH_UNDERSCORES for constants
* _single_leading_underscore for protected methods / internal functions
* Docstring formatting: [NumPy style](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_numpy.html)

## Testing
* Python: [Pytest](https://doc.pytest.org/)
* Code should have tests at the smallest function size possible (unit tests)
* Every new feature/Pull Request should have tests
* TravisCI integration
    * Each commit/branch/PR
* [Consider test-driven development](https://en.wikipedia.org/wiki/Test-driven_development)

## License
* [Apache Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt)
