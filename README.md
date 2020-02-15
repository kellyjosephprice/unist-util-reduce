# unist-util-reduce

[![Chat][chat-badge]][chat]

[**unist**][unist] utility to recursively reduce a tree

## Install

[npm][]:

```bash
npm install unist-util-reduce
```

## Usage

```javascript
var u = require("unist-builder");
var reduce = require("unist-util-reduce");

var tree = u("tree", [
  u("leaf", "1"),
  u("node", [u("leaf", "2")]),
  u("void"),
  u("leaf", "3")
]);

reduce(tree, function(node) {
  console.log(node);
  return node;
});
```

Yields:

```js
{ type: 'leaf', value: '1' }
{ type: 'leaf', value: '2' }
{ type: 'node' }
{ type: 'void' }
{ type: 'leaf', value: '3' }
```

## API

### `reduce(tree, transform)`

- `tree` - A node of type `Parent`
- `transform` - A function with the signature:
  - `(node: Node, path: number[], root: Paretn) => Node | Node[]`

## Related

- [`unist-util-visit-parents`][vp]
  — Like `visit`, but with a stack of parents
- [`unist-util-filter`](https://github.com/eush77/unist-util-filter)
  — Create a new tree with all nodes that pass a test
- [`unist-util-map`](https://github.com/syntax-tree/unist-util-map)
  — Create a new tree with all nodes mapped by a given function
- [`unist-util-remove`](https://github.com/eush77/unist-util-remove)
  — Remove nodes from a tree that pass a test
- [`unist-util-select`](https://github.com/eush77/unist-util-select)
  — Select nodes with CSS-like selectors

## Contribute

See [`contributing.md` in `syntax-tree/.github`][contributing] for ways to get
started.
See [`support.md`][support] for ways to get help.

This project has a [Code of Conduct][coc].
By interacting with this repository, organisation, or community you agree to
abide by its terms.

## License

[MIT][license] © [Callum Macdonald / GeneroUS Labs](https://github.com/GenerousLabs/unist-util-reduce)

<!-- Definition -->

[chat-badge]: https://img.shields.io/badge/chat-spectrum-7b16ff.svg
[chat]: https://spectrum.chat/unified/syntax-tree
[npm]: https://docs.npmjs.com/cli/install
[license]: licensea