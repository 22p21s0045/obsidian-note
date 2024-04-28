#lecture-5


## Navigation Guard

```js
router.beforeEach(async (to,from) =>{

const isMember = await authen()

if(!isMember && to.name!== 'Login'){

  return '/login'

}

})

console.log(isMember);
```


## Global State
- Must share and many component want to use

![](https://i.imgur.com/c91DFCx.png)


## Pinia

### Config main.js
```js
import { createPinia } from 'pinia'

import App from './App.vue'

const app = createApp(App)

app.use(router)

app.use(createPinia())
```

### Accept HMR update
```js
if(import.meta.hot){

    import.meta.hot.accept(acceptHMRUpdate(useTodos,import.meta.hot))

}
```


## Form Data