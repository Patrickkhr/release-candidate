<script>
    import { FAQuestions } from '$lib/index'
    export let itemCollection
  </script>
  
  <svelte:head>
    <title>Veelgestelde Vragen</title>
  </svelte:head>
  
  <FAQuestions {itemCollection} />
  