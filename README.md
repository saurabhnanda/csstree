<img align="right" width="111" height="111"
     alt="CSSTree logo"
     src="https://cloud.githubusercontent.com/assets/270491/19243723/6f9136c6-8f21-11e6-82ac-eeeee4c6c452.png"/>

# CSSTree

[![NPM version](https://img.shields.io/npm/v/css-tree.svg)](https://www.npmjs.com/package/css-tree)
[![Build Status](https://travis-ci.org/csstree/csstree.svg?branch=master)](https://travis-ci.org/csstree/csstree)
[![Coverage Status](https://coveralls.io/repos/github/csstree/csstree/badge.svg?branch=master)](https://coveralls.io/github/csstree/csstree?branch=master)
[![Join the CSSTree chat at https://gitter.im/csstree/csstree](https://badges.gitter.im/csstree/csstree.svg)](https://gitter.im/csstree/csstree)
[![Twitter](https://img.shields.io/badge/Twitter-@csstree-blue.svg)](https://twitter.com/csstree)

[Fast](https://github.com/postcss/benchmark) detailed CSS parser

> Work in progress. Project in alpha stage since AST format is subject to change.

- [Parsing CSS into AST](docs/parsing.md)
- [AST format](docs/ast.md)
- [Translate AST to string](docs/translate.md)
- [AST traversal](docs/traversal.md)
- [Utils to work with AST](docs/utils.md)
- [Working with syntax](docs/syntax.md)
- API references:
    - [Tokenizer](docs/Tokenizer.md)
    - [Parser](docs/Parser.md)
    - [Lexer](docs/Lexer.md)
    - [List](docs/List.md)

Docs and tools:

* [AST Explorer](https://astexplorer.net/#/gist/244e2fb4da940df52bf0f4b94277db44/e79aff44611020b22cfd9708f3a99ce09b7d67a8) – explore CSSTree AST format with zero setup
* [CSS syntax reference](https://csstree.github.io/docs/syntax.html)
* [CSS syntax validator](https://csstree.github.io/docs/validator.html)

Related projects:

* [csstree-validator](https://github.com/csstree/validator) – NPM package to validate CSS
* [stylelint-csstree-validator](https://github.com/csstree/stylelint-validator) – plugin for stylelint to validate CSS
* [Grunt plugin](https://github.com/sergejmueller/grunt-csstree-validator)
* [Gulp plugin](https://github.com/csstree/gulp-csstree)
* [Sublime plugin](https://github.com/csstree/SublimeLinter-contrib-csstree)
* [VS Code plugin](https://github.com/csstree/vscode-plugin)
* [Atom plugin](https://github.com/csstree/atom-plugin)

## Install

```
> npm install css-tree
```

## Usage

```js
var csstree = require('css-tree');
var ast = csstree.parse('.example { world: "!" }');

csstree.walk(ast, function(node) {
    if (node.type === 'ClassSelector' && node.name === 'example') {
        node.name = 'hello';
    }
});

console.log(csstree.translate(ast));
// .hello{world:"!"}
```

## License

MIT

Syntax matching use [mdn/data](https://github.com/mdn/data) by Mozilla Contributors
