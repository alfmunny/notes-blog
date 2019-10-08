---
title: Vue with Bootstrap
toc: true
date: 2018-06-13 20:09:57
tags: [notes]
categories: [posts]
---

Here is how to import boostrap in Vue.

## create the app

```
vue init webpack app
cd app
npm run dev
```

## install jquery, popper and boostrap

```
npm install jquery popper.js bootstrap --save
```
## webpack

Edit in file `build/webpack.base.conf.js`

```js webpack.base.conf.js
module.exports = {
    entry: {},
    output: {},
    resolve: {},
    module: {},

    plugins: [new webpack.ProvidePlugin({
        jQuery: 'jquery',
        $: 'jquery',
        jquery: 'jquery'
    })]
}
```

## import in main.js

```js main.js
require('bootstrap')
require('../node_modules/bootstrap/dist/css/bootstrap.min.css')
```

Try the navbar in the app. It should work.

## how to import a third party library

Take axios as an example
```
npm install axios --save
```

```js main.js
import axios from 'axios'
Object.definePrototype(Vue.prototype, '$axios', { value: axios })
```


