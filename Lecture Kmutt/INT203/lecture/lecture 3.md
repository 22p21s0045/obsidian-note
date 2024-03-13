3/13/2024
[[Chapter7-FetchAPI.pdf]]
#vue #emit #teleport
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



