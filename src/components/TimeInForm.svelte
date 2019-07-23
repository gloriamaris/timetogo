<script>
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
</script>

<form class="col s8 offset-s4">
  <div class="row">
    <div class="input-field col s2">
      <select>
        {#each hours as hour}
          <option value={hour}>{hour}</option>
        {/each}
      </select>
    </div>
    <div class="input-field col s2">
      <select>
        {#each minutes as minute}
          <option value={minute}>{minute}</option>
        {/each}
      </select>
    </div>
    <div class="input-field col s2">
      <select>
        <option value="AM">AM</option>
        <option value="PM">PM</option>
      </select>
    </div>
  </div>
</form>
