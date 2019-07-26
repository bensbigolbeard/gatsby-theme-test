#### Gastby theme/plugin issue

Bare-bones structure to demonstrate issue when a Gastby theme has a local plugin and is installed as a theme in another project/directory.

Structure based on [Building a Theme](https://www.gatsbyjs.org/tutorial/building-a-theme/) tutorial, including using Yarn workspaces to manage the sibling projects, `gatsby-theme-test` and `site`.

To trigger issue:

1. run `yarn workspace gatsby-theme-test` to install packages
2. run `yarn workspace gatsby-theme-test develop` to see it successfully pass `load plugins` build step
3. run `yarn workspace site` to install packages (including `gatsby-theme-test`)
4. run `yarn workspace site develop` or `cd site && gatsby develop` to see it fail the `load plugins` build step displaying this error:

```bash
ERROR

UNHANDLED REJECTION Unable to find plugin "gatsby-local-plugin". Perhaps you need to install its package?



  Error: Unable to find plugin "gatsby-local-plugin". Perhaps you need to install its package?
  - load.js:109 resolvePlugin
    [test-gatsby-theme]/[gatsby]/dist/bootstrap/load-plugins/load.js:109:11
  ...
```
