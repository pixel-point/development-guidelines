# Development Guidelines

**Before starting to work on the project, please check out the project's SASS variables and mixins, dependencies, and shared components.**

**Before starting to work on a specific section, please try to find a similar section that has already been built and make sure that your code looks and works as similar as the code of this section.**

**Before requesting a review, please double-check that everything works fine, the code is in good quality and everything from this page is completed.**

## Working with Git and Github

### Git basics

Git, simply put, is a tool to save versions of your code. You absolutely want to know at least a basic workflow and Git’s core features, different ways to undo changes or save multiple versions of a project, and how to collaborate with other team members.

If you don't feel confident using Git yet, you should spend some time exploring [Github's learning center](https://try.github.io/). There you can find more that enough resources to expand your Git knowledge

#### Git commands cheat sheet

There are tons of Git cheat sheets out there in the web, but in case you still don't have a favourite one, you might want to try [this](https://github.com/trein/dev-best-practices/wiki/Git-Tips), which covers just about all things you really need to know in order to start working effectively from the day one.

#### Git workflow

Git workflow is a kind of an instruction for how to use Git to accomplish work in a consistent and productive manner. It contains recommendations on introducing changes, solving conflicts, using branches, and more.

Though there is a number of workflows available, we mostly use **Github Workflow**:

1. Make sure your `master` branch is up to date
2. Create a separate feature branch with descriptive name, e.g. `feature/user-authentication`
3. Make your changes
4. Push the feature branch to remote repo
5. Make a PR to `master` branch, request a peer code review from your colleague
6. After you've passed it successfully, merge it!

<details>

<summary> :books: Read more on Git Workflows </summary>

_Mandatory:_

- [GitHub Workflow visualization](https://guides.github.com/introduction/flow/)

_Optional:_

- [Git Workflows overview by Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows)
- [Git Workflows overview on Git documentation portal](https://git-scm.com/docs/gitworkflows)

</details>

### Issues

Usually we don't use issues if the Pixel Point team members are the only one who currently works on the project, but we during this period we do use Notion's kanban board for similar purposes, so the concept is roughly the same.

Three common uses for Github issues:

1. **Reporting a bug with the project**
2. **Proposing a new feature or change**
3. **Discussing tactical and strategic issues with other stakeholders**, i.e. “should we switch from moment.js to date-fns.js because moment.js is declared to be sealed recently?”

Here’s what all of these have in common: they give other developers and stakeholders on the team a chance to weigh in and share information before code gets done.

You’re a single developer - you’re only as effective up to the limits of your own knowledge, talent, and experience. When you create an issue on Github or Notion and get into communication with your team members you can leverage the collective knowledge of everyone else. You will routinely save yourself hours of wasted effort if you get into communication early.

**Use issues templates**

Every project contains issues templates. They may somewhat differ from project to project, but they share some strictly defined structure which is mandatory to follow filling it up.
You can explore examples of issues in [this repo](https://github.com/pixel-point/development-guidelines/tree/master/.github/ISSUE_TEMPLATE).

**Use permalinks when discussing code**

One of the [most effective tools to come to Github is the permalink](https://help.github.com/en/articles/getting-permanent-links-to-files)- the ability to quickly reference an entire section of code and drop it into a Github issue so it can be unambiguously shared with the team at large.

Github permalinks provide a high degree of easily accessible context and they do it inexpensively. They make your technical communication more precise and reduce the cost of fix bugs and address design questions. Use them liberally.

**Use issue labels sparingly**

Github issue labels are a great tool that makes it easy to organize and aggregate similar kinds of issues quickly.

However, the trick with labels is to use them tersely. For instance, we have a “critical” label we apply on bugs that have created downtime for end-users - if we applied “critical” to every single issue then the label becomes meaningless.

Useful labels, when used sparingly, make it really easy to slice and dice the set of open issues into independent categories.

<details>
<summary>:books: Read more on issues:</summary>

_Optional:_

- [GitHub's Mastering Issues Guide](https://guides.github.com/features/issues/)

</details>

### Pull requests

#### Don't postpone the PR until the job is done

We believe, that the most effective way to use pull requests is to get code out in front of other developers on your team early and often, before you’ve invested too much development time into something new. If you’re going down the wrong path or if your work is in conflict with someone else’s it’s better for everyone to have that conversation early.

Put pull requests in front of the team as soon, as possible - this way you can get feedback quickly and leverage the knowledge and experience of your team right away, rather than when it’s too late.

#### Avoid “monster” Pull Requests; keep them "atomic" too

We prefer making PRs conceptually similar to our commits, that is, clear, small and concise, unless other project-specific conventions come to the scene, because:

- Each pull request is relatively small and independent, which makes the commit history more granular and easier to manage;
- Code reviews can be conducted quickly;
- You can get CI to run on each successive commit you add to your pull request, which helps you debug as you go; and
- You can work on multiple tasks concurrently while previous pull requests are waiting to be reviewed.

This strategy decreases the human costs associated with developing software: it allows for other team members to comment early (avoid blind alleys) and gives them smaller units of code to review (faster iteration speed.)

#### Review Your Own Pull Requests

It may sound like a daunting task and unproductive due to author bias, but in reality self-review brings huge benefits:

- You'll have a chance to fix typos, spot dead code or bad naming
- You might come up with a more elegant solution to your problem
- You might perform some insta-refactor before you reviewers spend time on pointing at the necessity of this

Remember, you, the pull request author, are the person in the room who knows the most about why you wrote your own code this way. Share that information with the rest of the team to help eliminate guesswork and speculation.

<details>
<summary>:books: Read more on Pull Requests</summary>

_Optional:_

- [Github's PRs Best Practices](https://github.community/t/best-practices-for-pull-requests/10195)
- [The (written) unwritten guide to pull requests by Atlassian](https://www.atlassian.com/blog/git/written-unwritten-guide-pull-requests)

</details>

### Commits

#### Commit related changes

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. Small commits make it easier for other developers to understand the changes and roll them back if something went wrong. Leverage the Git's staging area.

#### Keep commits "atomic"

“Atomic commit” is basically a fancy way of saying a commit that commits one and only one thing. It’s a single complete unit of work.

There are three basic features a commit needs to have to be atomic:

1. **Single, irreducible unit**
   Every commit pertains to one fix/feature/refactoring.

2. **Everything works**
   Commit shouldn't break the build on any commit.

3. **Clear and concise**
   Purpose is clear from commit message and description

<details>
<summary>:books: Read more on atomic commits:</summary>

_Optional:_

- [Wiki page](https://en.wikipedia.org/wiki/Atomic_commit)
- [# Developer Tip: Keep Your Commits “ATOMIC” by Sean Patterson](https://www.freshconsulting.com/atomic-commits/)

</details>

#### Use conventional commits

The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of.

We opted in for CC because they make it easier for team members to work on projects by allowing them to explore a more structured commit history. Also CC comes in handy when we want to automate routine tasks on certain projects, such as generating CHANGELOG, triggering build and publishing processes, determining a semantic version bump etc.

<details>
<summary> :heavy_exclamation_mark: Examples</summary>

![image](https://user-images.githubusercontent.com/20713191/93302208-0af33700-f813-11ea-8d5d-ea4fae2ef8ab.png)

</details>

<details>

<summary> :books: Read more on atomic commits: </summary>

_Mandatory_

- [Conventional Commits Specification](https://www.conventionalcommits.org/)

_Optional:_

- [Wiki page](https://en.wikipedia.org/wiki/Atomic_commit)

</details>

#### Commit often

Committing often keeps your commits small and, again, helps you commit only related changes. Moreover, it allows you to share your code more frequently with others. That way it‘s easier for everyone to integrate changes regularly and avoid having merge conflicts. Having large commits and sharing them infrequently, in contrast, makes it hard to solve conflicts.

Often commits also make code review much more pleasant. You’ll be able to review commit by commit, which will give your brain less information overload and offer a clear context of what you’re reviewing.

## Code

We try to keep our code as clean and as obvious as possible and we ask you to do the same.

1. We try to avoid using unnecessary styles. Any styles that can be deleted from the CSS should be deleted.
2. We try to keep our styles as simple as possible in order to make them be as clean, obvious, and understandable as possible.
3. We try to use the same naming everywhere it is possible to avoid any confusion. Here is a bunch of words we use for our classes: wrapper, inner, title, subtitle, description, text, button, illustration, image, logo, icon.
4. We try to avoid using shortcuts in our styles where it is possible. E.g. if we need to set the background color, we use `background-color`, if we need to set top and bottom paddings, we use `padding-top` and `padding-bottom`, if we need to set border radius for a specific corner, we use, for example, `border-top-right-radius`.
5. We try to use SASS variables everywhere where it is possible. We always have font styles and common colors in SASS variables that should always be used. Before starting to work on the project, make sure that you check what SASS variables the project has.
6. We try to use round numbers in our styles where it is possible since our designers try to do the same when creating the design of the website. Mostly it concerns paddings and margins.
