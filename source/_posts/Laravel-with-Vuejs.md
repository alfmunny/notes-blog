---
title: Laravel with Vuejs
date: 2017-06-23 18:23:26
tags: [laravel]
categories: [posts]
toc: true
---

## Laravel Mix

Use `laravel-mix` to integrate Vuejs with Laravel. See this [tutorial](https://laracasts.com/series/learn-vue-2-step-by-step/episodes/23) for reference.

### Install

```
npm install --save-dev laravel-mix
```

You can also run `npm install` in the working dir of laravel app


### Vue component

By default, you have already an example in the folder `resources/assets`


```js resources/assets/js/app.js

require('./bootstrap');

window.Vue = require('vue');

/**
 * Next, we will create a fresh Vue application instance and attach it to
 * the page. Then, you may begin adding components to this application
 * or customize the JavaScript scaffolding to fit your unique needs.
*/

import Example from './components/Example';

// or you can write
//Vue.component('example', require('./components/Example.vue'));


const app = new Vue({
    el: '#app',
    components: { Example }
});

```

```html resources/assets/js/components/Example.vue

<template>
    <div>
        I'm an example component!
    </div>
</template>

<script>
export default {
    mounted() {
        console.log('Component mounted.')
    }
}
</script>

```

### Import Vue instance

Create an index page `index.blade.php`

Import the javasript.

```html resources/views/index.blade.php
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta name="csrf-token" content="{{ csrf_token() }}">
        <title>log Searcher</title>
        <link rel="stylesheet" href="/css/app.css"> 
    </head>
    <body>
        <div id="app">
            <Home></Home>
        </div>
        <script src="/js/app.js"></script>
    </body>
</html>

```
Create the route

```php web.php
Route::get('/', function () {
    return view('index');
});

```

Visit myapp.dev. You got the vue app integrated.


### Configure Mix

Configure the file `webpack.mix.js`

```js webpack.mix.js
let mix = require('laravel-mix');

mix.js('resources/assets/js/app.js', 'public/js')
   .sass('resources/assets/sass/app.scss', 'public/css');

```


You can also change the webpack configuration by copying the file 
`node_modules/laravel-mix/setup/webpack.config.js` to working dir and customize it.

Change the entry in the package.json from
```json package.json
"development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
```

to


```
"development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=jebpack.config.js",
```



