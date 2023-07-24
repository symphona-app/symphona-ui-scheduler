# React Component Library Project Template

## Rationale

There are many bundlers out there in the wild that are geared towards bootstrapping projects for front-end projects,
such as Vite and Webpack. However, I wanted to create a similar, opinionated experience for projects that are just
simply
component libraries.

## Features

* TypeScript everything! No need to touch low-level configurations. Linters, formatters, and compilers should all work
  out of the box.
* Storybook included as an integral part of the developer workflow.
* Scripts configured and optimised for publishing to NPM.

## How to use this Template

1. This is a Github template repository. To get started click the big green "Use this template" button at the top of the
   page. [More detailed information about repository templates here.](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template)
2. Once you've created your repository, replace the `name` and `description` in the `package.json` file with your own
   information.
3. Write your component code in the `/src` directory. Good quality linting should be available to you out of the box.
4. (Optional) Write stories for your components. By running `npm run storybook` you can work on your components and
   their documentation with
   fast-refresh. This template uses Storybook's default
   configuration. [Storybook docs](https://storybook.js.org/docs/react/get-started/why-storybook)
5. You can format your codebase with `npm run format` to provide consistent style across your codebase.
5. When you're ready to publish you can do so with `npm publish`. You don't need to worry about building your project
   manually, this will be handled for you.
6. (Optional) You can also build your Storybook static website with `npm run build-storybook`. This produces
   no-dependency HTML that you can share with your users.

### Working with Jetbrains IDEs (Webstorm, Intellij et al)

You may require additional configuration when working with Jetbrains IDEs. My recommendation is to:

* Ensure that the ESLint and Prettier plugins are both enabled (they should be installed and enabled by default)
* Set the ESLint's plugin settings to be "automatic", it is most likely disabled by default.
* Set the Prettier plugin settings to "manual" and tick the "Run on 'reformat code' action" checkbox. Again, this is
  most likely disabled to begin with.

## FAQs

**Can I use absolute imports in my project?**

**A:**  I wouldn't recommend it. Whilst it may be more convenient initially during your development phase, it will most
likely lead to broken imports once your publish the package on NPM. Usually this would be achieved by specifying
a `baseUrl` in the `tsconfig.json` file, however that file won't be available in the final package.

**How do I have more control over which files go into the final package?**

**A:** By default, every file in your `/src` directory along with some root-level files will be published in the final
build. Non-TS files will be
transpiled (along with their type declarations) and every other file will be moved as-is. If you want to leave any files
out of the final build, you can do so by specifying a pattern in the `.npmignore` file. As an example, the `assets`
folder is currently ignored by the final build. **_Note 
that some files will be published or ignored irrespective of your settings, as NPM will override it._**