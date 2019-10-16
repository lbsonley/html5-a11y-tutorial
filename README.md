# Front End Skills - Junior Front End Developer

A collection of tutorials which demonstrate the technical skills required of a Junior Front End Developer and Unic in order to be considered for promotion to Professional Level.

## How to Use this Repository

This repository is organized into Modules. A Module is a series of Exercises which demonstrate a specific skill set required of a Junior Front End Developer. Each Exercise enhances features from the previous Exercise. Likewise, each Module will build upon the features from the previous module.

* Modules are organized into branches (i.e. `git checkout module/html5-a11y`)
* Exercises are tagged (i.e. `git checkout html5-a11y-ex-<exercise-number>`)

If you get stuck on a certain Exercise or want to jump ahead to a specific skill, you can use the correct command from below.

## Modules, Exercises and their Tags

In order to checkout a completed Module or completed Exercise, use the following commands.

Module | Checkout Module | Checkout Exercise |
---| ---| ---
Module 1: HTML5 and Accessibility | `git checkout module/html5-ally` | `git checkout html5-a11y-ex-<exercise-number>`
Module 2: CSS and Responsive Web Design (RWD) | `git checkout module/css-rwd` | `git checkout css-rwd-ex-<exercise-number>`
Module 3: JS and Browser Debugging | `git checkout module/js_debug` | `git checkout js-debug-<exercise-number>`

In order to see the entire solution for a Module:

```sh
git checkout module/html5-a11y
```

In order to see the solution for a specific Exercise:

```sh
git checkout html5-a11y-ex-1
```

## Saving Your Work

*As you work through the Exercises, it is better to save your own work upon completing an Exercise or Module rather than checking out the solution. Especially if you want to have your code reviewed.*

Before you begin to work on a module, you should create a `branch` to isolate your work.

```sh
# checkout desired Exercise of a module
git checkout html5-a11y-ex-0

# create a branch for your work
git checkout -b developer/<your-name>

# push your branch to the remote
git push -u origin $(git rev-parse --abbrev-ref HEAD)
```

As you complete each Exercise/Module, you should commit your code into your branch.

```sh
# add all changed files to commit
git add .

# create a commit message
git commit -m 'html5-a11y-ex-1'

# push to remote
git push origin
```

If you get stuck and you need to peak at the solution. Make sure you commit your changes before checking out the `tag`. Then you can go back to your branch and continue working.

```sh
# add all changed files to commit
git add .

# create a commit message
git commit -m 'html5-a11y-ex-1--partial'

# checkout solution
git checkout html5-a11y-ex-1

# go back to your branch and continue working
git checkout developer/<your-name>
```

## Local Setup

To get started working on these Skills, you need to clone this repository onto your computer.

```sh
git clone https://git.unic.com/scm/feskill/fe-skills-jr.git
cd fe-skills-jr
```

Then we need to install dependencies.

```sh
nvm use
npm install
```

Once you have installed the dependencies, you can start up the dev environment and get started with the Modules/Exercises.

```sh
npm start
```

## Working on Modules

At the root of this project, you will find a directory called `modules` which contains a directory for each module. Inside of each module directory you will find directions walking you through each exercise. Let's get started with [Exercise 1 in `html5-a11y`](modules/html5-a11y/ex-1.md).

## Motivation

I hope these Modules and Exercises will make it easier for you to gain the necessary skills to climb the maturity ladder. Take your time working through the Exercises, there are often links to external resources, take the time to read through them. It is better to develop a deep understanding of these core concepts early as it will make the more advanced subjects easier later.

## Errata / Improvements

If you find errors or would like to suggest an improvement to any of the Modules/Exercises, please read the [Contribution Guide](CONTRIBUTING.md) and then open a Pull Request.
