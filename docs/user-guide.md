# User Guide

All information for developers using `vapjs-util` should consult this document.

## Install

```
npm install --save vapjs-util
```

## Usage

```js
const util = require('vapjs-util');

const value = util.intToBuffer(38272);

// returns <Buffer ...>
```

## Available Methods

```
arrayContainsArray   <Function (Array, Array) : (Boolean)>
getBinarySize        <Function (String) : (Number)>
toBuffer             <Function (String) : (Buffer)>
intToBuffer          <Function (Number) : (Buffer)>
isHexPrefixed        <Function (String) : (Boolean)>
stripHexPrefix       <Function (String) : (String)>
padToEven            <Function (String) : (String)>
intToHex             <Function (Number) : (String)>
```

## Why BN.js?

`vapjs` has made a policy of using `BN.js` across all of its repositories. Here are some of the reasons why:

  1. lighter than alternatives (BigNumber.js)
  2. faster than most alternatives, see [benchmarks](https://github.com/indutny/bn.js/issues/89)
  3. used by the Vapory foundation across all [`vaporyjs`](https://github.com/vaporyjs) repositories
  4. is already used by a critical JS dependency of many vapory packages, see package [`elliptic`](https://github.com/indutny/elliptic)
  5. purposefully **does not support decimals or floats numbers** (for greater precision), remember, the Vapory blockchain cannot and will not support float values or decimal numbers.

## Browser Builds

`vapjs` provides production distributions for all of its modules that are ready for use in the browser right away. Simply include either `dist/vapjs-util.js` or `dist/vapjs-util.min.js` directly into an HTML file to start using this module. Note, an `vapUtil` object is made available globally.

```html
<script type="text/javascript" src="vapjs-util.min.js"></script>
<script type="text/javascript">
vapUtil(...);
</script>
```

Note, even though `vapjs` should have transformed and polyfilled most of the requirements to run this module across most modern browsers. You may want to look at an additional polyfill for extra support.

Use a polyfill service such as `Polyfill.io` to ensure complete cross-browser support:
https://polyfill.io/

## Latest Webpack Figures

Hash: 28b387e39e1016183a78                                                         
Version: webpack 2.1.0-beta.15
Time: 734ms
            Asset     Size  Chunks             Chunk Names
    vapjs-util.js  65.1 kB       0  [emitted]  main
vapjs-util.js.map  79.3 kB       0  [emitted]  main
    + 8 hidden modules

> vapjs-util@0.1.1 build:umd:min /home/nick/github/vapjs-util
> cross-env BABEL_ENV=commonjs NODE_ENV=production webpack --config ./internals/webpack/webpack.config.js ./lib/index.js --progress

Hash: 4d26e1d501227158f8ab                                                         
Version: webpack 2.1.0-beta.15
Time: 1523ms
            Asset     Size  Chunks             Chunk Names
vapjs-util.min.js  25.6 kB       0  [emitted]  main
    + 8 hidden modules

## Other Awesome Modules, Tools and Frameworks

 - [web3.js](https://github.com/vaporyco/web3.js) -- the original Vapory swiss army knife **Vapory Foundation**
 - [vaporyjs](https://github.com/vaporyjs) -- critical vaporyjs infrastructure **Vapory Foundation**
 - [browser-solidity](https://vapory.github.io/browser-solidity) -- an in browser Solidity IDE **Vapory Foundation**
 - [wafr](https://github.com/silentcicero/wafr) -- a super simple Solidity testing framework
 - [truffle](https://github.com/ConsenSys/truffle) -- a solidity/js dApp framework
 - [embark](https://github.com/iurimatias/embark-framework) -- a solidity/js dApp framework
 - [dapple](https://github.com/nexusdev/dapple) -- a solidity dApp framework
 - [chaitherium](https://github.com/SafeMarket/chaithereum) -- a JS web3 unit testing framework
 - [contest](https://github.com/DigixGlobal/contest) -- a JS testing framework for contracts

## Our Relationship with Vapory & VaporyJS

 We would like to mention that we are not in any way affiliated with the Vapory Foundation or `vaporyjs`. However, we love the work they do and work with them often to make Vapory great! Our aim is to support the Vapory ecosystem with a policy of diversity, modularity, simplicity, transparency, clarity, optimization and extensibility.

 Many of our modules use code from `web3.js` and the `vaporyjs-` repositories. We thank the authors where we can in the relevant repositories. We use their code carefully, and make sure all test coverage is ported over and where possible, expanded on.
