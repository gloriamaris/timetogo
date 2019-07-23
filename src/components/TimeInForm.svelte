<script> 
  import { afterUpdate } from 'svelte'
  export let timeOut;

  let isDefaultTimeIn = true    
  let hours = []    
  let minutes = []    

  for (let i = 0; i <= 12; i++) {
    let hr = i < 10 ? `0${i}` : `${i}`
    hours.push(hr)
  }

  for (let i = 1; i <= 59; i++) {
    let min = i < 10 ? `0${i}` : `${i}`
    minutes.push(min)
  }

  const toggleButton = () => {
    isDefaultTimeIn = !isDefaultTimeIn
  }

  $: hour = 0
  $: minute = 0
  $: meridiem = 'AM'

  afterUpdate(() => {
      console.log({ hour, minute, meridiem })
      console.log({ timeOut })
  })
  
</script>

<form class="col s8 offset-s4">
  <div class="row">
    <div class="input-field col s2">
      <select bind:value={hour}>
        {#each hours as hr}
          <option value={hr}>{hr}</option>
        {/each}
      </select>
    </div>
    <div class="input-field col s2">
      <select bind:value={minute}>
        {#each minutes as min}
          <option value={min}>{min}</option>
        {/each}
      </select>
    </div>
    <div class="input-field col s2">
      <select bind:value={meridiem}>
        <option value="AM">AM</option>
        <option value="PM">PM</option>
      </select>
    </div>
  </div>
</form>
