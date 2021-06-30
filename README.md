# typescript-project-template

A basic typescript project template, for those who aren't always sure where to start. Comes with:

- typescript with a tsconfig.json
- eslint
- prettier
- esbuild

This project is configured to use either `esbuild` or `tsc`. The preference is yours. In the current form, they both output CommonJS and ESM outputs. However, it can be modified to output however you'd like, such as for a browser.

## Linting

To lint, run the following:

```
yarn lint
```

## Building

This repo can build using the following interchangeably:

- esbuild
- tsc

In the case of `esbuild`, it will bundle as well, and run `tsc` only for typechecking.

### esbuild

```
npm run build
```

This will run typechecking with `tsc`, and will output two formats with `esbuild`:

- CommonJS (cjs)
- ES Module (esm)

These are shown in the `esbuild.config.mjs` script. If you would like to output only ESM, only CJS, or only IIFE, simply modify that config file to suit your needs.

The `watch` command will run with the following:

```
npm run build:watch
```

## tsc

If you want to build using `tsc` only, and avoid `esbuild` altogether, instead run:

```
npm run tsc:build
```

This will output two formats:
This will run typechecking with `tsc`, and will output two formats with `esbuild`:

- CommonJS (cjs)
- ES Module (esm)

These are done using `tsc` itself, and can be modified in the `package.json` npm scripts as appropriate.

### Formats

This project, by default, will output two formats with `esbuild` or `tsc`:

- CommonJS (cjs)
- ES Module (esm)

Look at the `package.json`. Notice how the `main` and `module` keys point to the outputs found in `esbuild.config.mjs`. If you want to output only a specific format, you will need to modify those areas.
