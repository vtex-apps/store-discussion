# Contributing

This is the single contributing guide to help you contribute to any of Store Framework's repositories. Keep in mind that all contributions made in Store Framework repositories are open to the public. And the pull request + code review cycle is the same for core team members, engineers inside of VTEX, and external contributors.

One important point to make here is that we want our community to be as open and accessible as possible, and language should not be a barrier. Throughout this guide, we'll recommend you to open issues and pull requests in our repositories, both of which will include a writing step. If you're not comfortable writing in English, please feel free to do so in Portuguese.

## Bugs

If you've found a bug or something is not behaving in the way you expected it to, feel free to [open an issue](https://github.com/vtex-apps/store-discussion/issues/new/choose) **after** you've checked to see if anyone else already reported the same bug. This is important to make it easier for us to track these issues. We'll do our best to review them and let you know when we're working on a fix.

Please provide us with as much information as possible. Here are a few things that help us investigate a bug:

1. A workspace where we can reproduce the bug consistently.
2. If the bug seems to be related to a certain block/component: include a snippet of the JSON from the store's theme that configures the block.
3. If you are using custom React components: try to reproduce the bug using only our native ones and report your findings in the issue.
4. If you believe the bug is related to some native apps installed in your store: include in the issue the app version currently installed. If it is related to multiple apps: include the version of each app.

## API Changes and Feature Requests

If you intend to change the [public API](#what-is-considered-a-public-api) or make any non-trivial changes to the implementation, please open a new issue describing in as much detail as possible the motivation for the changes and how you plan on implementing it. This lets us reach an agreement on your proposal before you put significant effort into it, and also gives our Product Managers the chance to review your proposal from a Product standpoint. This also allows us to understand how your changes might impact other stores using the framework.

Even if you’re only fixing a bug, we still recommend opening an issue detailing what you’re fixing. This is helpful in case we don’t accept that specific fix but want to keep track of the issue, and also helps us understand how many people are experiencing the same issues.

### What is considered a public API?

It might not be clear at first glance what we are talking about when we say *public APIs* in Store Framework, so here's a list to make it clearer:

1. If a component is exported by an IO app in some way, either being used in an `interfaces.json` file or as a React component, its **props** are considered the component's API.
2. If a function is exported by an IO app and can be imported into another app, this function is part of the app's public API.
3. CSS handles.
4. Message IDs that are declared in the `messages` folder and used by a component.
5. Exported TypeScript types and interfaces.
6. Store Framework interfaces declared in an `interfaces.json` file.
7. Any JavaScript or TypeScript files in the root of the `/react` folder since they can all be imported by other IO apps as named exports.  Note that renaming any of those files is a breaking change.

## Creating a Pull Request

The core Store Framework team is constantly monitoring for new pull requests. However, it's important to note, that currently it's a manual job, and we have lots of repositories to watch. It might take us some time to get to your pull request.

If this is your first time opening a PR in GitHub, check out this free video course from Kent C. Dodds: [How to Contribute to an Open Source Project on GitHub](https://app.egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github). If you prefer to read a guide in Portuguese, check out this article from GitHub: [Como Contribuir para o Open Source](https://opensource.guide/pt/how-to-contribute).

After you've already created an issue and discussed what you want to implement into the framework, you can go to the repository containing the app you want to change and follow these steps:

1. Fork the repository to your account and create a branch based on `master` (or main, depending on which is the name of the default branch).
2. Run `yarn` in the repository root. This will add code-style tools (Prettier and ESLint), git hooks using Husky, and testing tools. Note that these tools will use the configuration included in the repository you're working on. **Do not** change or ignore configuration files since they will make sure you're following our development patterns and speed up the review process.
3. Run `yarn` inside the `/react` and/or `/node` folders. This will install the necessary dependencies for the app itself.
4. Make your changes.
5. Ensure that the test suite passes. Run `yarn test` in the repository root to run all tests in the app. In some apps, running this command in the root will give you an error saying that there's no such command. In this case, run `yarn test` inside the `/react` or `/node` folders.
6. Make sure your code is formatted properly by running `yarn lint` in the repository root.
7. Update the `[CHANGELOG.md](http://changelog.md)` file. Our changelog files are written following the pattern described at [https://keepachangelog.com/en/1.0.0/](https://keepachangelog.com/en/1.0.0/).

    To make your PR easier to merge and avoid getting notified by conflicts every time a change to the changelog is made, make sure to place your entry**directly** below the `[Unreleased]` header, with no empty line in between.Here's an example:

    ```markdown
    ## [Unreleased]
    ### Added
    - Something new. Notice that there's no empty line above this one.

    ### Fixed
    - Something else. You should only use empty lines to separate headers.
    
    ## [1.0.0] - 2017-06-20
    ### Added
    - This was already here before my changes.
    ```

8. Update the app's documentation accordingly. You can find it in the `/docs` folder.
9. Create your pull request. During this step make sure to fill out the whole pull request template, including a workspace where we can test your implementation and, if applicable, screenshots that might also help us.
10. Tag the Store Framework team (`@vtex-apps/store-framework-devs` on GitHub) for review.

    ![store-framework-review-request](https://user-images.githubusercontent.com/27777263/132237790-6e1c6110-96b7-419d-812f-e13c64433a2c.gif)

## Documentation

Documentation plays a significant role in Store Framework. We always try our best to keep it accurate and up to date. With that in mind, we only consider releasing changes to any of our apps after they're properly documented. So make sure to always include any necessary changes to documentation in your pull requests.

If you spot any outdated or wrong information in any of our docs, please feel free to open a pull request to update it, no issue needs to be created in this case.

## Store Framework Office Hours

Office Hours is a weekly one-hour meeting with community members, the core team, and other VTEXers. It's a great opportunity to talk to us, get help, and give us some feedback about the framework.

The event is open to everyone and you are always welcome! Important to note that the event is conducted in Portuguese, but if you don't speak the language, no worries. You can come and ask us your questions in English.

To participate in the event, join [this Zoom room](https://vtex.zoom.us/j/96795350497?pwd%3DSzBYY25FdnQrSkdwbWtKQVh3K2lWdz09&sa=D) at Tuesdays 4PM GMT-3 (Brasília time).
 