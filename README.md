# Development Guidelines

**Before starting to work on the project, please check out the project's SASS variables and mixins, dependencies, and shared components.**

**Before starting to work on a specific section, please try to find a similar section that has already been built and make sure that your code looks and works as similar as the code of this section.**

**Before requesting a review, please double-check that everything works fine, the code is in good quality and everything from this page is completed.**

## Commits

1. We use Conventional Commits for commit messages. You can read more about Conventional Commits [here](https://www.conventionalcommits.org/en/v1.0.0/). [Here](https://cheatography.com/albelop/cheat-sheets/conventional-commits/) you can find a useful Conventional Commits Cheat Sheet.
2. We try to make our commits "atomic". [Here](https://www.freshconsulting.com/atomic-commits/) and [here](https://en.wikipedia.org/wiki/Atomic_commit) you can read more about Atomic commits.

## Pull Requests

Pull requests should contain:

1. A clear name that briefly describes what this pull request does. The name should follow the same format that commits do. E.g. feat(components): add News for Home, fix(components): fix animation in Hero for Home.
2. A clear description that fully describes what this pull request does. Additionally,
    1. If this pull request brings some visual changes, e.g. a new section, then this pull request also should contain a screenshot of this section and the link where this section can be found and tested by the reviewer.
    2. If this pull request contains some additional changes, e.g. a small fix for another section or something else, this should be documented in the description too.

Pull requests should be "atomic" too. One task = one pull request. E.g. one section = one pull request, a bunch of fixes for the page is one pull request and another bunch of fixes for another page is a different pull request.

## Code

We try to keep our code as clean and as obvious as possible and we ask you to do the same.

1. We try to avoid using unnecessary styles. Any styles that can be deleted from the CSS should be deleted.
2. We try to keep our styles as simple as possible in order to make them be as clean, obvious, and understandable as possible.
3. We try to use the same naming everywhere it is possible to avoid any confusion. Here is a bunch of words we use for our classes: wrapper, inner, title, subtitle, description, text, button, illustration, image, logo, icon.
4. We try to avoid using shortcuts in our styles where it is possible. E.g. if we need to set the background color, we use `background-color`, if we need to set top and bottom paddings, we use `padding-top` and `padding-bottom`, if we need to set border radius for a specific corner, we use, for example, `border-top-right-radius`.
5. We try to use SASS variables everywhere where it is possible. We always have font styles and common colors in SASS variables that should always be used. Before starting to work on the project, make sure that you check what SASS variables the project has.
6. We try to use round numbers in our styles where it is possible since our designers try to do the same when creating the design of the website. Mostly it concerns paddings and margins.
