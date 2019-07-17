<button on:click class="{classes}">
  {text}
  <slot></slot>
</button>
<script>
  export let text = "";
  export let classes = "btn btn-sm";
</script>
