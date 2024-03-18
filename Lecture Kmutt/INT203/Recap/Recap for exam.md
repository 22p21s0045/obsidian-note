for exam 4/02/2024
#recap 
## Reactive attribute

```js
import { ref } from 'vue';
// Define a reactive value 
const count = ref(0); 
// Update the count value count.value++; 

// Access and log the updated count value 
console.log(count.value);
```

Using `ref` allows you to create reactive values in Vue.js, where changes to the value are automatically tracked and reflected in the view. Remember to access and modify the value using `.value` when working with `ref`.