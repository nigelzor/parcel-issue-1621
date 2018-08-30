# parcel-issue-1621

minimal reproduction of [parcel issue 1621](https://github.com/parcel-bundler/parcel/issues/1621)

build fails when transitively importing lodash-es through typescript, but not when importing through javascript.

```
$ parcel build --experimental-scope-hoisting src/index.html
🚨  ../node_modules/lodash-es/isPlainObject.js does not export 'default'
    at replaceExportNode (/parcel-issue-1621/node_modules/parcel-bundler/src/scope-hoisting/concat.js:54:13)
    at ReferencedIdentifier (/parcel-issue-1621/node_modules/parcel-bundler/src/scope-hoisting/concat.js:317:20)
    at newFn (/parcel-issue-1621/node_modules/babel-traverse/lib/visitors.js:318:17)
    at NodePath._call (/parcel-issue-1621/node_modules/babel-traverse/lib/path/context.js:76:18)
    at NodePath.call (/parcel-issue-1621/node_modules/babel-traverse/lib/path/context.js:48:17)
    at NodePath.visit (/parcel-issue-1621/node_modules/babel-traverse/lib/path/context.js:105:12)
    at TraversalContext.visitQueue (/parcel-issue-1621/node_modules/babel-traverse/lib/context.js:150:16)
    at TraversalContext.visitSingle (/parcel-issue-1621/node_modules/babel-traverse/lib/context.js:108:19)
    at TraversalContext.visit (/parcel-issue-1621/node_modules/babel-traverse/lib/context.js:192:19)
    at Function.traverse.node (/parcel-issue-1621/node_modules/babel-traverse/lib/index.js:114:17)
```
