# typescript-project-template

A basic typescript project template, for those who aren't always sure where to start. Comes with:

- typescript with a tsconfig.json
- eslint
- prettier
- esbuild

This project does use `esbuild`, which might not be your preference. You can rip it out, and use `tsc` as normal if necessary. However, the performance gains when you start writing a lot of typescript may be worth it.

## Linting

To lint, run the following:

```
yarn lint
```

## Building

This repo uses a mix of `esbuild` for building and bundling, and `tsc` for typechecking. To build, simply run:

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

If you want to build using `tsc` only, and avoid `esbuild` altogether, instead run:

```
npm run tsc:build
```

### Formats

This project, by default, will output two formats with `esbuild`:

- CommonJS (cjs)
- ES Module (esm)

Look at the `package.json`. Notice how the `main` and `module` keys point to the outputs found in `esbuild.config.mjs`. If you want to output only a specific format, you will need to modify those areas.
