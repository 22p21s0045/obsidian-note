3/6/2024
#props
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

## child component is read only
## If you not use v-bind when pass props it <mark class="hltr-yellow">pass string</mark> 