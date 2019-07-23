<script>
  import TimeInForm from './TimeInForm.svelte'
  export let timeIn = new Date()
	export let workHours = 9
  export let timeOut = new Date(timeIn.setHours(timeIn.getHours() + workHours)).toLocaleTimeString('en-US')

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
    <TimeInForm />
  </div>
</div>
