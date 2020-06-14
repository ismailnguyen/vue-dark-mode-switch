<template>
  <div id="app">
    <DarkModeSwitch @switched="onSwitched"/>
  </div>
</template>

<script>
	import DarkModeSwitch from './components/DarkModeSwitch.vue'

	export default {
		name: 'App',
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
