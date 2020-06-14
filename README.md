# vue-dark-mode-switch

## Install
```
npm install --save vue-dark-mode-switch
```

### Usage

Import the `DarkModeSwitch` component, and it will emit its state through `@switched` event method.

```html
<template>
    <DarkModeSwitch @switched="onSwitched" />
</template>

<script>
	import DarkModeSwitch from './components/DarkModeSwitch.vue'

	export default {
		components: {
			DarkModeSwitch
		},
		methods: {
			onSwitched: function (isSwitched) {
				console.log('dark mode is enabled :', isSwitched);
			}
		}
	}
</script>
```