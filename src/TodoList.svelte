<div class="row justify-content-center">
  <div class="col-xs-12 col-sm-6 col-md-5 col-lg-4">
    <h1 class="text-center text-uppercase text-secondary my-4">{name}</h1>
    <div class="form-group">
      <div class="input-group mb-3">
        <input type="text" 
               class="form-control" 
               placeholder="Todo item" 
               aria-label="Todo item" 
               aria-describedby="button-addon2"
               bind:value={newItemText} />
        <div class="input-group-append">
          <button disabled={btnDisabled} 
                  on:click={addItem} 
                  class="btn btn-outline-secondary" 
                  type="button" id="button-addon2">Add
          </button>
        </div>
      </div>      
    </div>
     {#if items.length > 0}
      <ul class="list-group">
        {#each items as item, i (item.id) }
          <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="">{item.text}</span>
            <SButton on:click={ () => removeItem(item) }>
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="none" d="M0 0h24v24H0V0z"/><path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12 19 6.41z"/></svg>
            </SButton>
          </li>
        {/each}
      </ul>
      {/if}     
  </div>
</div>

<script>
  import { guid }  from "./utils.js"
  import SButton from "./SButton.svelte"

  export let name;

  let items = [{ id: 111, text: "Svelte"},{ id: 222, text: "is"}, { id: 333, text: "cool"}];
  let newItemText = "";

  $: btnDisabled = newItemText === '' ? "disabled": ''

  function addItem() {
    const item = { id: guid(), text: newItemText}
    items = [...items, item]
    newItemText = "";
  }
  function removeItem(item) {
    items = items.filter(m => m.id !== item.id)
  }
</script>
<style>
  
</style>