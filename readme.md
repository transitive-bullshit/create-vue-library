# create-vue-library

> CLI for creating reusable, modern Vue libraries using Rollup and create-vue-app.

[![NPM](https://img.shields.io/npm/v/create-vue-library.svg)](https://www.npmjs.com/package/create-vue-library) [![Build Status](https://travis-ci.com/transitive-bullshit/create-vue-library.svg?branch=master)](https://travis-ci.com/transitive-bullshit/create-vue-library) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Status

**This project is an active WIP**. It is a fork of [create-vue-library](https://github.com/transitive-bullshit/create-vue-library).


## Features

- Easy-to-use CLI
- Handles all modern JS features
- Bundles `cjs` and `es` module formats
- [Rollup](https://rollupjs.org/) for bundling
- [Babel](https://babeljs.io/) for transpiling
- [Jest](https://facebook.github.io/jest/) for testing
- Supports complicated peer-dependencies
- Optional support for TypeScript
- Sourcemap creation
- Hundreds of public modules created
- Thorough documentation :heart_eyes:


## Install

This package requires `node >= 4`, but we recommend `node >= 8`.

```bash
npm install -g create-vue-library
```


## Creating a New Module

```bash
create-vue-library
```

Answer some basic prompts about your module, and then the CLI will perform the following steps:
- copy over the template
- install dependencies via yarn or npm
- link packages together for local development
- initialize local git repo

At this point, your new module should resemble this screenshot and is all setup for local development.


## Development

Local development is broken into two parts (ideally using two tabs).

First, run rollup to watch your `src/` module and automatically recompile it into `dist/` whenever you make changes.

```bash
npm start # runs rollup with watch flag
```

The second part will be running the `example/` create-vue-app that's linked to the local version of your module.

```bash
# (in another tab)
cd example
npm start # runs create-vue-app dev server
```

Now, anytime you make a change to your library in `src/` or to the example app's `example/src`, `create-vue-app` will live-reload your local dev server so you can iterate on your component in real-time.

![](https://media.giphy.com/media/12NUbkX6p4xOO4/giphy.gif)


#### Publishing to NPM

```bash
npm publish
```

This builds `cjs` and `es` versions of your module to `dist/` and then publishes your module to `npm`.

Make sure that any npm modules you want as peer dependencies are properly marked as `peerDependencies` in `package.json`. The rollup config will automatically recognize them as peers and not try to bundle them in your module.


#### Deploying to Github Pages

```bash
npm run deploy
```

This creates a production build of the example `create-vue-app` that showcases your library and then runs `gh-pages` to deploy the resulting bundle.


## License

MIT © [Travis Fischer](https://github.com/transitive-bullshit)
