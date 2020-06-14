<template>
  <div id="app">
    <DarkModeSwitch :switched="onSwitched"/>
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
			onSwitched: function () {
				console.log('dark mode enabled !')
			}
		}
	}
</script>
