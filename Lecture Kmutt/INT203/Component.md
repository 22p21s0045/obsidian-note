![[Pasted image 20240228104634.png]]
In SFCs, it's **recommended** to use <mark style="background: #FF5582A6;">PascalCase</mark> tag names for child components to differentiate from native HTML elements.


# Global register component
```js
const app = createApp(App)

app.component('Footer',Footer)

app.mount("#app")
```

<mark style="background: #FF5582A6;">Disadavatage</mark> It cannot tree shaking

# Slot
![[Pasted image 20240228111232.png]]

- Sent markup from parent to child


```js
<template>
  <div class="card">
    <h2 v-if="title">{{ title }}</h2>
    <slot name="header" />
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
};
</script>

```

```js
<template>
  <div>
    <Card title="My Card">
      <p>This is the content for the unnamed slot.</p>
      <template v-slot:header>
        <h2>Custom Header</h2>
      </template>
    </Card>
  </div>
</template>

```

![[Pasted image 20240228111844.png]]

![[Pasted image 20240228112044.png]]

Design footer 
- Slot content ซ้าย กลาง ขวา