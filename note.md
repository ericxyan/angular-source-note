## Module
CommonJS API: https://nodejs.org/api/modules.html#modules_modules_commonjs_modules
### require()
> Node.js Modules: https://nodejs.org/docs/v0.4.2/api/modules.html

- Core Modules: `require('http')`
Defined in node's source `lib/` folder
- File Modules: `require('my-service')`, `require('../../my-class')`
  - Try `.js` then `.node`(`dlopen`).
  - If not starting with path `/`,`./` etc., try to load from upper levels' `node_modules` until not found.
  - $HOME/.node_modules: Always included, even has {paths} set.
  - $HOME/.node_libraries
  - $PREFIX/lib/node: `$PREFIX` is Node.js configured `node_prefix`
- Folder Modules: `require('my-library')`
  - Try to load `main` in `package.json` in `./my-library/` folder
  - Try to load `./my-library/index.<js|node>` file.
- Custom paths: `require.paths: string[]` to specify searching folders
  > Not recommended
  

### Caching
Modules are cached after the first time they are loaded.

### Main
When a file is run directly from Node.js, `require.main` is set to its `module`.
````
# node foo.js
require.main === module
true

# require('foo')
require.main === module
false
````
### Cycles

## Node.js Multi Threading
> `child_process`: https://nodejs.org/api/child_process.html
`spwanSync`


