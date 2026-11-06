# Contributing to MotifJS Community projects

Thanks for helping. This file applies to every repository in the `motifjs-community` organization unless
the repository has its own `CONTRIBUTING.md`.

## Before you start

- **Questions and ideas** go to [Discussions in the main repository](https://github.com/motifjsdev/motifjs/discussions).
- **Bugs** in a package go to that package's issues. Use the bug template and include a minimal reproduction:
  a StackBlitz link or a small repository.
- **Bugs in MotifJS itself** (`@motifx/core`, `@motifx/compiler`) belong in
  [motifjsdev/motifjs](https://github.com/motifjsdev/motifjs/issues). If you are not sure, open it in the
  package repository and we will move it.
- For anything larger than a small fix, open an issue first so we can agree on the approach.

## Working on a repository

Every repository follows the same layout and commands:

```sh
npm install
npm test            # Vitest + jsdom
npm run typecheck   # tsc --noEmit
npm run lint:jsx    # motif-lint (MJX005 and friends)
npm run build
```

The MotifJS rules a change follows, in short:

- `view()` runs once. Reactive reads must be fields (`{state.count}`) or getters (`{() => a + b}`).
- Lowercase DOM names: `class`, `onclick`, `for`.
- Lists map over arrays of objects with a stable `key`.
- `x-wait` / `x-display` keep component state; `{cond && <X/>}` rebuilds the component.
- Timers, sockets and third-party instances are registered with `this.motif.setDisposable`.

The full rules are at [motifjs.com/llms.txt](https://motifjs.com/llms.txt).

## Pull requests

- One topic per pull request. Keep unrelated formatting changes out.
- Add or update tests for behaviour changes. A public component needs at least a render test and a basic
  interaction test.
- Add a line under `## [Unreleased]` in `CHANGELOG.md`.
- CI must be green: tests, typecheck, `motif-lint` and the example build.
- Commit messages: short, imperative, in English (`Fix focus loss when the list is filtered`).

## Code style

- TypeScript strict, ESM only, named exports.
- Public components are classes: `class X extends Component<HTMLElement, XProps>`; props that can change
  are typed `Bind<T>` and read with `read()`.
- Every exported symbol has a JSDoc comment: two sentences and a short example.
- Comments explain why, not what. Where MotifJS behaves differently from React, say so in one line.

## License

By contributing you agree that your contribution is licensed under the MIT license of the repository.
