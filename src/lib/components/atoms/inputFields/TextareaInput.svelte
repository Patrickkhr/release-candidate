<script>
  export let id;
  export let name;
  export let placeholder = "";
  export let required = false;
</script>

<label for={id}><slot /></label>
<textarea id={id} name={name} placeholder={placeholder} {required}></textarea>

<style>
  textarea {
    width: 100%;
    padding: 0.625em;
    border: none;
    border-radius: 5px;
    background-color: #fff;
    color: #000;
  }
  label {
    color: white;
  }
</style>
