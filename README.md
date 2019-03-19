[![npm](https://img.shields.io/npm/v/@nomiclabs/buidler-solpp.svg)](https://www.npmjs.com/package/@nomiclabs/buidler-solpp)
 [![Build Status](https://travis-ci.com/nomiclabs/buidler-solpp.svg?branch=master)](https://travis-ci.com/nomiclabs/buidler-solpp)


# buidler-solpp
[Buidler](http://getbuidler.com) plugin for integration with [solpp preprocessor](https://github.com/merklejerk/solpp).

## What
This plugin hooks into the compilation pipeline and run the solpp preprocessor.

## Installation
```
npm install @nomiclabs/buidler-solpp
```

And add the following require to the top of your ```buidler.config.js```:

```require("@nomiclabs/buidler-solpp")```

## Tasks
This plugin creates the task ```solpp``` and overrides the ```compile:get-source-paths```.

The task ```solpp``` receives an array of files and the solpp config options and it does the actual preprocessing.

The ```compile:get-source-paths``` task is part of the compilation pipeline and it will be executed everytime you compile your contracts with buidler.


## Environment extensions
This plugin does not extend the environment.

## Usage
There are no additional steps you need to take for this plugin to work. Install it, run `npx buidler compile` and solc will compile the solpp generated contracts, which they will be in ```cache/solpp-generated-contracts```.

# Configuration

You may want to define your symbols or any other solpp configuration option in your project's ```buidler.config.js```. 

```defs```: is an object where each property is the symbol's name and its value is the actual definition. Definitions can be numbers, string, expressions, lists, or functions. For more detail about symbols you can check [solpp README](https://github.com/merklejerk/solpp).
```cwd: string```: directory where the contracts are located, it will be used for flattening purposes, by default it will be the project's source directory.
```collapseEmptyLines: boolean```: delete empty lines, false by default.
```noPreprocessor: boolean```: disable preprocessor, false by default.
```noFlatten: boolean```: won't flatten contracts, true by default.
```tolerant: boolean```: ignore if an imported contract file is missing when flattening, false by default.

