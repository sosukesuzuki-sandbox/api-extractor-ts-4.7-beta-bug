# api-extractor-ts-4.7-beta-bug

This is a repository to reproduce `@microsoft/api-extractor` not working with `typescript@4.7.0-beta`.

This repository contains two directories, `ts-4.6` and `ts-4.7`.

These two directories are npm packages that use TypeScript and `@microsoft/api-extractor`. The only difference is the version of typescript.

In the `ts-4.6` directory, the `api-extractor run` succeeds, but in the `ts-4.7` directory it fails.

## In `ts-4.6`

```sh
npm i

npm run build

> ts-4.6@1.0.0 build
> tsc

npm run api-extractor

> ts-4.6@1.0.0 api-extractor
> api-extractor run --local --verbose


api-extractor 7.21.3  - https://api-extractor.com/

Using configuration from ./config/api-extractor.json
Analysis will use the bundled TypeScript version 4.6.3
Writing: /Users/s.suzuki/development/api-extractor-ts-4.7-beta-bug/ts-4.6/temp/ts-4.6.api.json
The API report is up to date: temp/ts-4.6.api.md
Writing package typings: /Users/s.suzuki/development/api-extractor-ts-4.7-beta-bug/ts-4.6/dist/ts-4.6.d.ts
Warning: src/index.ts:1:1 - (ae-missing-release-tag) "foo" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)

API Extractor completed successfully
```

## In `ts-4.7-beta`

```sh
npm i

npm run build

> ts-4.7-beta@1.0.0 build
> tsc

npm run api-extractor

> ts-4.7-beta@1.0.0 api-extractor
> api-extractor run --local --verbose

api-extractor 7.21.3  - https://api-extractor.com/

Using configuration from ./config/api-extractor.json
Analysis will use the bundled TypeScript version 4.7.0-beta

ERROR: Internal Error: Missing Program.getDiagnosticsProducingTypeChecker
You have encountered a software defect. Please consider reporting the issue to the maintainers of this application.
```
