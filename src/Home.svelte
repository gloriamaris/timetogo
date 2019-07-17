<script>
  export let timeOut;
  let isDefaultTimeIn = true;

  const toggleButton = () => {
    isDefaultTimeIn = !isDefaultTimeIn;
  };

  document.addEventListener("DOMContentLoaded", function() {
    var elems = document.querySelectorAll(".timepicker");
    var instances = M.Timepicker.init(elems, { defaultTime: "now" });
  });
</script>

<div class="container">
  <div class="row">
    <div class="col s12 m7">
      <div class="card horizontal">
        <div class="card-stacked">
          <div class="card-content">
            <h2>{timeOut}</h2>
            <h6>Going home in 6 hours!</h6>
          </div>
          <div class="card-action">
            {#if isDefaultTimeIn}
              <a
                class="waves-effect waves-light green accent-4 white-text btn"
                href="#"
                on:click={toggleButton}>
                <i class="material-icons left">access_time</i>
                Change time-in
              </a>
            {:else}
              <label>Change Time In</label>

              <div class="row">
                <div class="input-field col s5">
                  <select class="browser-default">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                  </select>
                </div>
                <div class="input-field col s5">
                  <select class="browser-default">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                  </select>
                </div>
                <div class="input-field col s2">
                  <select class="browser-default">
                    <option value="AM">AM</option>
                    <option value="PM">PM</option>
                  </select>
                </div>
                <div class="input-field col s12">
                  <a class="waves-effect waves-light btn right-align">OK</a>
                </div>
              </div>
            {/if}
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
