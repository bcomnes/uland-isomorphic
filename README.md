# uland-isomorphic
[![Actions Status](https://github.com/bcomnes/uland-isomorphic/workflows/tests/badge.svg)](https://github.com/bcomnes/uland-isomorphic/actions)

Isomorphic exports of [uland][uland]

```
npm install uland-isomorphic
```

## Usage

Use [uland][uland] or [uland-ssr][ssr] from a single import identifier depending on then environment you are running.

``` js
import {render, html, svg} from 'uland-isomorphic';
// const {render, html, svg} = require('uland');

render(document.body, html`<h1>Hello 👋 µhtml</h1>`);
```

## How

While @webreflection recomends [require-overrides](https://github.com/WebReflection/require-overrides/#readme) in the offical documentation, that requires special flags or transforms to work.

`uland-isomorphic` works by utilizing environment specific exports fields so that you can have dependency injection at the built-in module resolver layer.
It supports the following export fields:

- `main` (cjs node)
- `browser` (cjs browser)
- `exports.import` (esm node)
- `exports.reqire` (cjs node)
- `exports.browser` (esm browser)

## License

MIT

[uland]: https://github.com/WebReflection/uland
[ssr]: https://github.com/WebReflection/uland-ssr
