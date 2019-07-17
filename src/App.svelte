<script>
	import Home from './Home.svelte'
	export let timeIn = new Date()
	export let workHours = 9
	
	$: timeOut = new Date(timeIn.setHours(timeIn.getHours() + workHours)).toLocaleTimeString('en-US')
</script>

<style></style>

<Home timeOut={timeOut} />
