#lecture-3 
#env #fetch-api 

[[Chapter8-VueRouter.pdf]] 

![](https://i.imgur.com/RM6bMFS.png)

## Get data from env
```JS
console.log(import.meta.env.VITE_BASE_URL);
```

>[!tip]
>If data very sensitive please not use **'VITE_ '** on first
>

```
.env
.env.production
```
- .env for **run dev**
- .env.production for **run build**

#vue-router
## Vue Router

Client-side routing is used by single-page applications (SPAs) to tie the browser URL to the content seen by the user. As users navigate around the application, the URL updates accordingly, but the page doesn't need to be reloaded from the server.

Vue Router is built on Vue's component system. You configure **routes** to tell Vue Router which components to show for each URL path.

### Set up 
```js
import { createRouter, createWebHistory } from 'vue-router'

const history = createWebHistory()

const routes = [

    {

    }

]
```