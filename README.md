# Development Guidelines

## Table of Content

- [Before you begin](#before-you-begin)
- [Working with Git and Github](#working-with-git-and-github)
  - [Git basics](#git-basics)
    - [Git cheat sheet](#git-commands-cheat-sheet)
    - [Git workflow](#git-workflow)
  - [Commits](#commits)
    - [Use conventional commits](#use-conventional-commits)
    - [Keep commits "atomic"](#keep-commits-atomic)
    - [Commit related changes](#commit-related-changes)
    - [Commit often](#commit-often)
  - [Pull Requests](#pull-requests)
    - [Avoid "monster" pull requests](#avoid-monster-pull-requests-keep-them-atomic-too)
    - [Don't postpone a PR until the job is done](#dont-postpone-a-pr-until-the-job-is-done)
    - [Review your own PRs](#review-your-own-pull-requests)
  - [Issues](#issues)
    - [Use issue templates](#use-issue-templates)
    - [Use permalinks](#use-permalinks-when-discussing-code)
    - [Use issue labels](#use-issue-labels)
  - [Code](#code)
    - [General principles](#general-principles)
      - [Keep It Simple, Stupid](#keep-it-simple-stupid)
      - [You Aren't Gonna Need It](#you-arent-gonna-need-it)
      - [Don't repeat yourself](#dont-repeat-yourself)
      - [Don't reinvent the wheel](#dont-reinvent-the-wheel)
      - [Don't reinvent the wheel](#dont-reinvent-the-wheel)
    - [JavaScript](#javascript)
      - [Choose meaningful names](#choose-meaningful-names)
      - [Avoid "magic" values](#avoid-magic-values)
      - [Avoid mental mapping](#avoid-mental-mapping)
      - [Single-purpose functions](#single-purpose-functions)
      - [Avoid long list of arguments](#avoid-long-list-of-arguments)
    - [Styling](#styling)
      - [Keep naming consistent across the projects](#keep-naming-consistent-across-the-projects)
      - [Avoid properties shortcuts](#avoid-properties-shortcuts)
      - [Prefer variables over inline values](#prefer-variables-over-inline-values)
      - [Pursue reasonable pixel-perfect](#pursue-reasonable-pixel-perfect)
  - [Frameworks](#frameworks)
  - [3rd parties of choice](#3rd-parties-of-choice)
  - [Tooling](#tooling)
  - [Tips and Tricks](#tips-and-tricks)
- [Development guidelines contribution](#development-guidelines-contribution)

## Before you begin

- Before starting to work on the project, please check out the project's SASS variables and mixins, dependencies, and shared components.

- Before starting to work on a specific section, please try to find a similar section that has already been built and make sure that your code looks and works as similar as the code of this section.

- Before picking a 3rd party, make sure you are familiar with the our list [3rd parties of choice](./3rd-parties-of-choice/README.md) which contains best picks for a certain use cases

- Before requesting a review, please double-check that everything works fine, the code is in good quality and everything from this page is completed.

## Working with Git and Github

### Git basics

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

### Commits

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

#### Commit related changes

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. Small commits make it easier for other developers to understand the changes and roll them back if something went wrong. Leverage the Git's staging area.

#### Commit often

Committing often keeps your commits small and, again, helps you commit only related changes. Moreover, it allows you to share your code more frequently with others. That way it‘s easier for everyone to integrate changes regularly and avoid having merge conflicts. Having large commits and sharing them infrequently, in contrast, makes it hard to solve conflicts.

Often commits also make code review much more pleasant. You’ll be able to review commit by commit, which will give your brain less information overload and offer a clear context of what you’re reviewing.

### Pull requests

#### Avoid “monster” pull requests; keep them "atomic" too

We prefer making PRs conceptually similar to our commits, that is, clear, small and concise, unless other project-specific conventions come to the scene, because:

- Each pull request is relatively small and independent, which makes the commit history more granular and easier to manage;
- Code reviews can be conducted quickly;
- You can get CI to run on each successive commit you add to your pull request, which helps you debug as you go; and
- You can work on multiple tasks concurrently while previous pull requests are waiting to be reviewed.

This strategy decreases the human costs associated with developing software: it allows for other team members to comment early (avoid blind alleys) and gives them smaller units of code to review (faster iteration speed.)

#### Don't postpone a PR until the job is done

We believe, that the most effective way to use pull requests is to get code out in front of other developers on your team early and often, before you’ve invested too much development time into something new. If you’re going down the wrong path or if your work is in conflict with someone else’s it’s better for everyone to have that conversation early.

Put pull requests in front of the team as soon, as possible - this way you can get feedback quickly and leverage the knowledge and experience of your team right away, rather than when it’s too late.

#### Review your own pull requests

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
- </details>

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

**Use issue labels**

Github issue labels are a great tool that makes it easy to organize and aggregate similar kinds of issues quickly.

However, the trick with labels is to use them tersely. For instance, if we have a “critical” label that we apply on bugs that have created downtime for end-users - if we applied “critical” to every single issue then the label becomes meaningless.

Useful labels, when used sparingly, make it really easy to slice and dice the set of open issues into independent categories.

<details>
<summary>:books: Read more on issues:</summary>

_Optional:_

- [GitHub's Mastering Issues Guide](https://guides.github.com/features/issues/)

</details>

## Code

### General principles

Each developer in our team is expected to write code that is clean and maintainable. In order to achieve that we agreed upon following a number of well-known coding principles. These principles make yours and the life of other team members easier.

#### Keep It Simple, Stupid

We pursue a goal of keeping our code as clean, obvious and simple as possible. Don't get caught up in trying to be overly clever or showing off with a paragraph of advanced code. Make it easy to come back after six months and get right back to work.

<details>

<summary> :heavy_exclamation_mark: Examples</summary>

**A simple example to illustrate the point**

```
// pseudocode

(A ? B : C) // fine

A ? B ? C : D : E // what?

if A {
	B ? C : D
} else E // better
```

</details>

<details>

<summary>:books: Read more on KISS:</summary>

_Optional:_

- [KISS Principle on Wiki](https://en.wikipedia.org/wiki/KISS_principle)

</details>

#### You Aren't Gonna Need It

We do not solve problems that do not exist and want you to do the same. Never code for functionality on the chance that you may need it in the future.

<details>

<summary> :heavy_exclamation_mark: Examples</summary>

Imagine you were assigned to implement a simpler counter, like this one:

![Simplest counter possible](https://daveceddia.com/images/counter-plain.png)

What would be violation for YAGNI principle here? Implementing option in component that allows user to count in **real** numbers besides the **integers** because you thought that could come in handy in a future. Don't do that.

</details>

<details>

<summary>:books: Read more on YAGNI:</summary>

_Optional:_

- [YAGNI Principle on Wiki](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

</details>

#### Don't Repeat Yourself

We are constantly eliminating repeating code, starting from setting up projects variables in SCSS that contain all cross-project values like colors, shadows, font-sizes etc. all the way down to pieces of JS logic. If you see that something is repeating over and over or _clearly_ will be repeated, make a layer of abstraction.

Be aware of early abstractions though as it has a potential to violate the **YAGNI** principle.

<details>

<summary> :heavy_exclamation_mark: Examples</summary>

```scss
/* bad */

// in one component
.box {
  background-color: white;
}

// in another component
.item {
  border-color: white;
}

// in third component
.title {
  color: white;
}

/* good */

// define a global variable
$color-primary: white;

// in one component
.box {
  background-color: $color-primary;
}

// in another component
.item {
  border-color: $color-primary;
}

// in third component
.title {
  color: $color-primary;
}
```

</details>

<details>

<summary>:books: Read more on DRY:</summary>

_Optional_:

- [DRY principle on Wiki](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
</details>

#### Don't reinvent the wheel

We are not solving the problems that were already solved. Our projects have in common a lot of similar UI elements, logic, configs etc, so before working on something, answer the following questions:

- Was that particular thing implemented already in your current project? Can you reuse it? Can you make it reusable?
- Was that particular thing implemented already (therefore passed code review) in some other project? Can you reuse it?
- Does it make sense to add a 3rd party instead of writing it from the ground up?

Start the implementation only if you have 3 negative answers.

<details>

<summary> :heavy_exclamation_mark: Examples</summary>

**Example 1**
You have to create a reusable `Heading` component that will different behavior depending on passed props. Is it worth doing it? Nope, `Heading` exists in every single web project, so you better ask you team members in which project should you look into to take a decent one.

**Example 2**
You have to create a complex `Select` component with multi-selecting, option search etc. Is it worth doing it? Nope, you probably better pick `react-select` as a 3rd party since it has appropriate functionality and well-tested.

**Example 3**
You have to create a `LollipopGallery` component that will act as a modal window and display to user a random picture of lollipop, but on mobiles will be shown as an animated svg lollipop itself. No idea, why stakeholders would want to have that, but anyway, this is exact case where you can demonstrate your excellent dev skills.

<details>

<summary>P.S.</summary>
Still better check for OS projects, no one knows for sure.

![Lollipop](https://i.pinimg.com/280x280_RS/ee/96/2c/ee962ca94f6e042c1bea6a76058bcd94.jpg)

</details>

</details>

### JavaScript

:warning: On every single project there is a number of linters/formatter set up to ensure our code style is consistent. Always keep it enabled!

#### Choose meaningful names

Make sure your variables and functions are named meaningfully. This reduces the need for additional comments as your code speaks for itself.

Remember, variables should give an answer for **What is**, functions for **What does it do**

<details>

<summary>:heavy_exclamation_mark: Examples</summary>

```javascript
// bad
cosnt d = new Date();
// good
const date = new Date();

// bad
const mail = () => {}
// good
const sendEmails = () => {}
```

</details>

#### Avoid "magic" values

Each variable has to have an origin that is easy to find, otherwise that would be confusing on the reader’s end.

<details>

<summary>:heavy_exclamation_mark: Examples</summary>

```javascript
/* bad */
// Reader would have no clue on what 86400000 is
setTimeout(randomFunction, 86400000);
/* good */
// Declare them as capitalized named constants.
const MILLISECONDS_IN_A_DAY = 86_400_000;

setTimeout(blastOff, MILLISECONDS_IN_A_DAY);
```

</details>

#### Avoid mental mapping

Don't force people and your future self to memorize the variable context. Variables should be understood even when the reader has not managed to follow the whole history of how they came to be.

<details>

<summary>:heavy_exclamation_mark: Examples </summary>

```javascript
// bad
const names = ["John", "Jane", "Joseph"];
names.forEach((n) => {
  doStuff();
  doSomethingExtra();
  // ...
  // ...
  // ...
  // What is this 'n' for?
  dispatch(n);
});
// good
const names = ["John", "Jane", "Joseph"];
names.forEach((name) => {
  doStuff();
  doSomethingExtra();
  // ...
  // ...
  // ...
  // 'name' makes sense now
  dispatch(name);
});
```

</details>

#### Single-purpose functions

Avoid multiplying side effect in your functions. Distribute the logic between two/three/four - this way they could be understood and tested better.

<details>
<summary>:heavy_exclamation_mark: Examples </summary>

```javascript
// bad
const onFormSubmit = values => {
	// validate submitted values in place
	// send values to your backend
}
// good
const validate = values => {
	// validate submitted values
}
const onFormSubmit = values => {
	validate(values)
	// send values to your backend
```

</details>

#### Avoid long list of arguments

Ideally, you should avoid a long number of arguments. One or two arguments is the ideal case, and three or more should be consolidated in an object to ease the usage.

<details>
<summary>:heavy_exclamation_mark: Examples </summary>

```javascript
/* bad */

// utils.js
export const buildCTAMessage = (name, lastName, city, action) => // stuff
// index.js
import { buildCTAMessage } from './utils.js'

const data = {
	name: 'John',
	lastName: 'Doe',
	city: 'Dallas'
}
const action = 'play golf'

const ctaMessage = buildCTAMessage(
	// which one should go first?
	data.lastName,
	data.name,
	data.city,
	action
)

/* good */

// utils.js
export const buildCTAMessage = ({name, lastName, city, action}) => // stuff

// index.js
const data = {
	name: 'John',
	lastName: 'Doe',
	city: 'Dallas'
}
const action = 'play golf'

const ctaMessage = buildCTAMessage({
	// doesn't matter
	...data,
	action
})
```

</details>

### Styling

#### Keep naming consistent across the projects

We try to use the same naming everywhere it is possible to avoid any confusion. Here is a bunch of words we use for our classes: `wrapper`, `inner`, `title`, `subtitle`, `description`, `text`, `button`, `illustration`, `image`, `logo`, `icon`.

#### Avoid properties shortcuts

We try to avoid using shortcuts in our styles where it is possible. E.g. if we need to set the background color, we use `background-color`, if we need to set top and bottom paddings, we use `padding-top` and `padding-bottom`, if we need to set border radius for a specific corner, we use, for example, `border-top-right-radius`.

#### Prefer variables over inline values

We try to use SASS variables everywhere where it is possible. We always have font styles and common colors in SASS variables that should always be used. Before starting to work on the project, make sure that you check what SASS variables the project has. (DRY)

#### Pursue reasonable pixel-perfect

We try to use round numbers in our styles where it is possible and our designers try to do the same when creating the design of the website. Don't be that guy who puts `151px` magic values "just as in the mockup", `150px` will do just fine.

## Frameworks

Backbone of our toolset for actually building projects consists of the following frameworks, each of them has a separate section or a separate repo due to its complexity:

1. [ReactJs](./frameworks/react.md)
2. [GatsbyJs](https://github.com/pixel-point/gatsby-starter)
3. [NextJs](./frameworks/next.md)

## 3rd party of choice

We have a curated list of 3rd parties that we decided to use in certain cases, like `react-hook-form` for working with forms or `date-fns` for working with dates. It is always good to consult with this list before picking a 3rd party.

[See list of chosen 3rd parties ](./3rd-parties/README.md)

## Tooling

We have a curated list of miscellaneous tools that are of a great help for us in the development process, e.g. online image compressor or md editor. You might find it useful as well.

[See list of tools](./tools/README.md)

## Tips and Tricks

We also have a somewhat random collection of tips, tricks and gists that we consider worth keep under the hand.

[See collection](./tips-and-tricks/README.md)

## Development guidelines contribution

### Typo

If you spotted a typo, indentation or hierarchy inaccuracy, please, submit a PR or raise an issue.

### Content

If you think some piece of content is suboptimal, provides irrelevant info, redundant, obsolete or needs to be changed in some way, please, raise an issue.

### Structure

If you think the structure of guidelines could be improved, please, raise an issue.

### Other

If you have an idea how to make guidelines better, but for some reason can not use Github tools to let contributors know about it, don't hesitate to reach [Kirill Bolotsky](https://github.com/BolotskyDev) in Slack or [Telegram](https://t.me/bolotskydev)
