# MotifJS Community

Packages, tools and reference apps for **MotifJS** (`@motifx/core`), the UI framework whose view is a live object tree, not a description of one. There is no virtual DOM
and no template: the compiler turns JSX into code that builds component objects, and every element is an object you
can reach at every stage, from the constructor to a detached tree.

```tsx
import { Application, Component, reactive } from '@motifx/core';

class Counter extends Component<HTMLDivElement> {
  state = reactive({ count: 0 });
  view() {
    return <button onclick={() => this.state.count++}>Clicked {this.state.count} times</button>;
  }
}

Application.CreateBuilder().build().run('#app', new Counter());
```

## Start here

- Docs: [motifjs.com](https://motifjs.com) · for AI agents: [motifjs.com/llms.txt](https://motifjs.com/llms.txt)
- Framework: [motifjsdev/motifjs](https://github.com/motifjsdev/motifjs) (questions go to its Discussions)
- npm: [`@motifx/core`](https://www.npmjs.com/package/@motifx/core), [`@motifx/compiler`](https://www.npmjs.com/package/@motifx/compiler)

## Repositories

| Repository | What it is |
|------------|------------|
| [motifjs-ui](https://github.com/motifjs-community/motifjs-ui) | The component library: buttons, editors, lists, forms, DataGrid, Scheduler and more, in five design languages. Docs at [ui.motifjs.com](https://ui.motifjs.com) |
| [motifjs-design-system](https://github.com/motifjs-community/motifjs-design-system) | Design tokens, themes, base styles and the design languages every MotifJS component library builds on |
| [motifjs-data](https://github.com/motifjs-community/motifjs-data) | The data layer: `DataSource` and adapters for arrays, REST, OData v4 and WCF SOAP services |
| [motifjs-i18n](https://github.com/motifjs-community/motifjs-i18n) | Translations: an ICU subset, locales loaded when first used, `Intl` formatting, RTL |
| [motifjs-devtools](https://github.com/motifjs-community/motifjs-devtools) | The browser DevTools extension: the component tree, bindings and services of a running app |
| [docs](https://github.com/motifjs-community/docs) | The source of [motifjs.com](https://motifjs.com) |
| [skills](https://github.com/motifjs-community/skills) | Skills that teach a coding agent MotifJS |
| [chartjs](https://github.com/motifjs-community/chartjs) | Chart.js wrapper |
| [sortablejs](https://github.com/motifjs-community/sortablejs) | SortableJS wrapper for reactive lists |
| [powerpack](https://github.com/motifjs-community/powerpack) | Assorted helpers |

Every repository carries the [`motifjs`](https://github.com/topics/motifjs) topic.

## Contributing

Each repository has a `CONTRIBUTING.md` with its setup and checks; the
[organisation's one](https://github.com/motifjs-community/.github/blob/main/CONTRIBUTING.md) applies where a repository has none. Bugs go to the
repository's issues, questions and ideas to the [MotifJS discussions](https://github.com/motifjsdev/motifjs/discussions).

All code here is MIT licensed.
