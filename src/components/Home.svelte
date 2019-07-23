<script>
  import TimeInForm from './TimeInForm.svelte'

	const WORK_HOURS = 9
  let timeIn = new Date()
  $: timeOut = new Date(timeIn.setHours(timeIn.getHours() + WORK_HOURS)).toLocaleTimeString('en-US')

  document.addEventListener('DOMContentLoaded', function() {
		var elems = document.querySelectorAll('select');
		var instances = M.FormSelect.init(elems, {});
	})

</script>

<style>
  a {
    color: #9e9e9e;
  }
</style>

<div class="container">
  <div class="row center">
    <h1 class="teal-text">{timeOut}</h1>
  </div>
  <div class="row center">
    <div class="divider"></div>
    <h6 class="grey-text lighten-1">or change time in</h6>

    <TimeInForm bind:timeOut={timeOut}/>
  </div>
</div>
