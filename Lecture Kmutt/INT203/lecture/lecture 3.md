3/13/2024
[[Chapter7-FetchAPI.pdf]]
#vue #emit #teleport #lecture-3 
## Emits

![](https://i.imgur.com/ICDHQqI.png)

###  Define emit
```js
<script setup>
defineEmits(['inFocus', 'submit'])
</script>
```

```js
<script setup>
const emit = defineEmits(['inFocus', 'submit'])

function buttonClick() {
  emit('submit')
}
</script>
```

###  Call emit event

```js
<button @click="$emit('increaseBy', 1)">
  Increase by 1
</button>
```

### Pass Event in Emit

```js
<input type="text" @change="$emit('changeMe', $event.target.value)" />
```



![](https://i.imgur.com/9YxnDK2.png)

### Want add new value in parent and call function and use payload from child

![](https://i.imgur.com/gZtcF5a.png)



- Register 
- Call
#promise
## Fetch API

### Asynchronous
refers to something that is **not simultaneous or concurrent in time**. Let’s explore its meaning in different contexts:

### Synchronous Execution
- In synchronous execution, tasks are performed **sequentially**, one after the other.
    - When a process (let’s call it **Process A**) initiates a task, it **waits** for that task to complete before moving on to the next one.
    - Think of it like a relay race where one runner waits for the other to pass the baton before starting their leg.

### Promise