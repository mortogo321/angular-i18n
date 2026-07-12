# Angular i18n Demo

A minimal Angular application demonstrating a hand-rolled internationalization (i18n) approach: a translation service and pipe that load language strings from JSON files at runtime, without a third-party i18n library.

## What's inside

- `TranslateService` — fetches a language JSON file (`assets/i18n/<lang>.json`) via `HttpClient` and stores the resulting key/value map.
- `TranslatePipe` — an impure Angular pipe (`| translate`) that looks up a key in the loaded translation map, falling back to the raw key if not found.
- `AppComponent` — renders a title translated via the pipe and two buttons to switch between English and Japanese at runtime.
- Sample translation files for English (`en.json`) and Japanese (`jp.json`) under `src/assets/i18n/`.

## Tech stack

- Angular (standalone CLI project, TypeScript)
- RxJS
- Karma / Jasmine for unit tests
- Protractor for end-to-end tests

## Quickstart

```bash
yarn install
yarn start
```

Navigate to `http://localhost:4200/`.

Other scripts:

```bash
yarn build   # production build to dist/
yarn test    # unit tests via Karma
yarn e2e     # end-to-end tests via Protractor
yarn lint    # lint via ng lint
```

## Project structure

```
src/app/
  translate.service.ts   # loads and stores translation data
  translate.pipe.ts       # pipe used in templates to resolve a key
  app.component.ts/.html  # demo UI with language switch buttons
src/assets/i18n/
  en.json                 # English strings
  jp.json                 # Japanese strings
```
