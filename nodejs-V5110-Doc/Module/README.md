# Modules
- [Modules](./Modules)
  - [Accessing the main module](#Accessing_the_main_module)
  - [Addenda:Package Manager Tips](./Addenda:Package_Manager_Tips)
  - [All Together](./All_Together)
  - [Caching](./Caching)
    - Module Caching Caveats 
  - [Core Modules](./Core_Modules)
  - [Cycles](./Cycles)
  - [File Modules](./File_Modules)
  - [Loading from node_modules Folders](./Loading_from_node_modules_Folders)
  - [Loading from the global folders](./Loading_from_the_global_folders)
  - [The module Object](./The_module_Object)
    - module.children
    - module.exports
      - exports alias
    - module.filename
    - module.id
    - module.loaded
    - module.parent
    - module.require(id)


The semantics of Node.js's require() function were designed to be general enough to support a number of reasonable directory structures. Package manager programs such as dpkg, rpm, and npm will hopefully find it possible to build native packages from Node.js modules without modification.

Below we give a suggested directory structure that could work:

Let's say that we wanted to have the folder at /usr/lib/node/<some-package>/<some-version> hold the contents of a specific version of a package.

Packages can depend on one another. In order to install package foo, you may have to install a specific version of package bar. The bar package may itself have dependencies, and in some cases, these dependencies may even collide or form cycles.

Since Node.js looks up the realpath of any modules it loads (that is, resolves symlinks), and then looks for their dependencies in the node_modules folders as described here, this situation is very simple to resolve with the following architecture:

/usr/lib/node/foo/1.2.3/ - Contents of the foo package, version 1.2.3.
/usr/lib/node/bar/4.3.2/ - Contents of the bar package that foo depends on.
/usr/lib/node/foo/1.2.3/node_modules/bar - Symbolic link to /usr/lib/node/bar/4.3.2/.
/usr/lib/node/bar/4.3.2/node_modules/* - Symbolic links to the packages that bar depends on.
Thus, even if a cycle is encountered, or if there are dependency conflicts, every module will be able to get a version of its dependency that it can use.

When the code in the foo package does require('bar'), it will get the version that is symlinked into /usr/lib/node/foo/1.2.3/node_modules/bar. Then, when the code in the bar package c

#Accessing_the_main_module
Addenda:Package Manager Tips