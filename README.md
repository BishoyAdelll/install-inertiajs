# Project Title

Installation{laravel,inertia,vue3 }

## Description

How to install inertia in laravel (laravel,inertia,vue3 )

## Getting Started



### Installing

1. Follow this steps 


### Executing program

* Step-by-step 
```
laravel new inertia-demo
```
```
cd inertia-demo

```

* create
```
app.blade.php
@vite('resources/js/app.js')
@inertiaHead
@inertia
```
```
php artisan inertia:middleware 
* Go to kernel
```
App\Http\MiddleWare\HandleInertiaRequest::class,
```
```
npm install @inertiajs/vue3
```
```
npm install vue@next
```
```
npm install @vitejs/plugin-vue

```
```
*in vite.config.js 
import {vue} from '@vitejs/plugin-vue'
*and type this after laravel 
```
```
 vue({
            template:{
                transformAssetUrls:{
                    base:null,
                    includeAbsolute:false
                }
            }
        })

```
*resources->js->app.js
```
import { createApp, h } from 'vue';
import { createInertiaApp } from '@inertiajs/vue3';
createApp({
    resolve:name=>{
        const pages =import.meta.glob('./Pages/**/*.vue',{eager :true})
        return pages[`./Pages/${name}.vue`]
    },
    setup({el,App,props,plugin}){
        createApp({render:()=>h(App,props)})
        .use(plugin)
        .mount(el)
    },
})


```
*create directory called Pages inside js folder
*create your vue pages.
*and in your web.php 
*Ex
*return inertia::render(create)
this create its in Pages folder create.vue 
```

```
*finaly 
```
php artisan serve 
npm run dev
```

```


## Help

Follow the order

## Authors

Contributors names and contact info
{
    name:"Bishoy Adel "
}






