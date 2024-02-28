![[Pasted image 20240228091644.png]]
**1. Initialization:**

- **`beforeCreate`:** This hook is called first, before the component is even created. Here, you can perform initial setup tasks that don't rely on the component's existence, like defining computed properties or methods.
- **`created`:** The component has been created at this stage. You can access data and props here, but the DOM hasn't been manipulated yet. This is a good place to fetch data from an API or set up subscriptions to external events.

**2. Mounting:**

- **`beforeMount`:** This hook is called just before the component is mounted to the DOM. The DOM elements haven't been created yet, but the component instance is fully set up.
- **`mounted`:** This is a crucial hook, called after the component has been successfully mounted to the DOM. Now you can access DOM elements using refs or imperative DOM manipulation methods. This is the ideal place for code that relies on the DOM being present, like initializing third-party libraries or setting up event listeners.

**3. Updating:**

- **`beforeUpdate`:** This hook is called before the component re-renders due to data changes. You can make any necessary preparations before the DOM updates occur.
- **`updated`:** This hook is called after the component has been re-rendered and the DOM has been updated to reflect the latest data state. Be cautious when using this hook to mutate the component's state, as it can lead to infinite update loops. Instead, consider using `nextTick` if you need to access the updated DOM after a state change.

**4. Destruction:**

- **`beforeDestroy`:** Called just before the component is about to be destroyed and removed from the DOM. Use this hook to perform any cleanup tasks, like removing event listeners or unsubscribing from external subscriptions.
- **`destroyed`:** The component has been destroyed and removed from the DOM at this point. This hook is rarely used, but it can be helpful for debugging purposes or specific edge cases.
![[Pasted image 20240228092104.png]]
# Not use

- [ ] Before create
- [ ] created


# Before update / updated
Execute all time when dom have update

![[Pasted image 20240228093440.png]]
# beforeCreate 
เรียกหลังจากที่ CreateApp ถูกเรียก
# Created
เรียก script app.vue เสร็จเเล้ว

```js
import { createApp } from 'vue'

import App from './App.vue'

console.log("main.js Before Calling createapp() function");

const app = createApp(App)

app.mount("#app")

console.log("main.js After calling createApp() function");
```

# onBeforeMount 
after template compiled, dynamic placeholders and interpolations are removed and replaced with the values. The template and the styles are all compiled here, but the DOM cannot be manipulated yet.
<mark style="background: #FF5582A6;">Compile ตีความค่าต่างลง template</mark>


```js
onBeforeMount(()=>{

  console.log("At App.vue before mount");

  

})

onMounted(()=>{

  console.log("At App.vue on mounted");

  

})

// onCreated

console.log("At app.vue with script setup");

</script>
```

# Oncreated 
จะถูกทําเลย