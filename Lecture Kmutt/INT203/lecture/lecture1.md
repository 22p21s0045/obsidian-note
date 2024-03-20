3/6/2024
#props #slot #lecture-1 
# Props
- Configuration Props (mange style)
- Data Props (sent data)
- use <mark class="hltr-yellow">CamelCase</mark>
#syntax
# style Guide

```js
const props = defineProps(['errorMsg','randNumbers'])
```
- Optional
- Pass String

	## <mark class="hltr-red">Prop validation</mark>
	
	![](https://i.imgur.com/YsdvPcm.png)
	![](https://i.imgur.com/VoD1vM7.png)
<mark class="hltr-red">	Multiple possible type</mark>
	![](https://i.imgur.com/epK4nOV.png)
	<mark class="hltr-red">Customize</mark>
	![](https://i.imgur.com/NiOusJ9.png)
```js
const props = defineProps({

    size:{

        type:String,

        validator(value){

            return ['sm','md','lg'].includes(value)

  

        },

    },

    variant:{

        type:String,

        validator(value){

            return ['flat','tonal','outlined'].includes(value)

        }

    }

  

})
```


## child component is read only
## If you not use v-bind when pass props it <mark class="hltr-yellow">pass string</mark> 
#emit

One way data flow
- Read only parent change child is change
- If child want to change data
		- If want to use one time use <mark class="hltr-yellow">ref</mark>
		- If want parent state change use <mark class="hltr-yellow">computed</mark>

#slot
## Slot sent data to parent
```js Todolist.vue
 <ListModal :items="todos" v-slot="slotprops" >

    {{ slotprops.item }}

    <p>ID: {{ slotprops.item.id }}</p>

    </ListModal>
```

```js ListModal.vue
<template>

  <slot v-for="(item,index) in items" :key="index" :item ="item">

  

  </slot>

</template>
```
- <mark class="hltr-yellow">item</mark> it sent to slot-props


