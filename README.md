# tree-handle-lib

A small JavaScript utility library for tree data.

Package with `rollup.js`, exported as `esm` module.
![](https://raw.githubusercontent.com/wqs576222103/tree-handle-lib/main/images/preview.png)


## Install

```bash
npm install tree-handle-lib
// or
yarn add tree-handle-lib
// or
pnpm install tree-handle-lib
```

## API

examples:

```txt
check:
  checkNode
  unCheckNode
  changeAllCheck

equal:
  isEqualTreeNode

filter:
  filterTreeByName

find:
  findNodeByKey
  findAllKeys
  findChildKeysByKey
  findParentKeysByKey

insert:
  insertChild
  insertAfter
  insertBefore

list:
  list2Tree
  tree2List

remove:
  removeNodeByKey

sort:
  sortNodeByName
split:
  splitStrings2Tree

update:
  updateNodeByKey

```
- Detail Docs: [https://wqs576222103.github.io/tree-handle-lib-doc/](https://wqs576222103.github.io/tree-handle-lib-doc/)
## Usage

```javascript
import { findNodeByKey } from "tree-handle-lib";
// or use `const { findNodeByKey } = require('tree-handle-lib/dist/index.cjs.js')` as commonjs
const tree = [
      {
        id: '1',
        name: 'www',
        children: [],
      },
    ];
const node = findNodeByKey(tree, '1', "children", 'id');
```

Can also import like

```javascript
import treeHandleLib from "tree-handle-lib";

console.log(treeHandleLib.findNodeByKey); // Function
```

or like this, import from a child package

```javascript
import {findNodeByKey} from "tree-handle-lib/dist/find.js";

console.log(findNodeByKey); // Function
```


## Developer Compatibility
- node >=v14.6(pnpm requires at least Node.js v14.6)
- pnpm v7.18.2

## BUGS
- issue: [https://github.com/wqs576222103/tree-handle-lib/issues](https://github.com/wqs576222103/tree-handle-lib/issues)

## Developer Guide
1. create a module and file under src/lib directory.
2. create a tree handle function and export it by default.
3. add test unit in ./__test__  directory.
4. pnpm run build or pnpm run test.
  so that you can see there is an additional file has been added to the tmp directory and some changed in babel.config.cjs
5. you can only test the module you want, by edit jest.testMatch in package.json.
6. publish npm package. first using the pnpm version patch command, push the code to github, and create a release on github. it can auto publish package to npm.

## TODO
1. Realize the pure function form of implementing the method.
2. Build only the modules you are developing
3. Develop a scaffolding for automatically generating method modules and test samples
