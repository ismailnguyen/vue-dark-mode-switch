# vue-dark-mode-switch
VueJS Dark mode switch component

## Install
```shell
npm install --save vue-dark-mode-switch
```

## Usage
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

## Demo

Live : [https://www.ismailnguyen.com](https://www.ismailnguyen.com)

### Switch Off
![Switch Off](https://raw.githubusercontent.com/ismailnguyen/vue-dark-mode-switch/master/docs/assets/switch_off.png)

### Switch On
![Switch On](https://raw.githubusercontent.com/ismailnguyen/vue-dark-mode-switch/master/docs/assets/switch_on.png)