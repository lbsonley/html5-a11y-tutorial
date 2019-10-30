# Contributing Guidelines

Thank you for considering making a contribution. Before you get started on your Pull Request, please take a look through this guide to ensure your changes are compatible with the tutorial requirements.

## Tutorial Workflow

This repository is primarily used as a tutorial for developers at Unic to gain skills. As developers work thorugh the examples, they have the ability to preview the answers to Exercises by checking out out a specific `branch` or `tag`.

**Therefore, it is very important to maintain the separation of features by `branch` and `tag`.**

## Important Steps for Pull Requests

* Before making your changes, make sure that you have checked out the appropriate `tag`.

* Make a new branch based on this tag

```sh
git checkout html5-a11y-ex-1

git checkout -b feature/update-html5-a11y-ex-1
```

* Only make changes for one Exercise at a time.

* After making changes for a single Exercise
  * commit your code
  * update the tag
  * push your code with tags
  * open a PR against master and add Me as reviewer

* Update exercise instructions to reflect the changes (located in `docs/` directory)

* Update `docs/README.md` if necessary

```sh
git add .

git commit -m 'Update html5-a11y-ex-3'

git tag -f html-a11y-ex-3

git push origin --tags
```

That's it.

Thanks for your contribution!
