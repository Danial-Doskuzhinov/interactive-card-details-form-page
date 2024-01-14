<!-- App.svelte -->

<script>
  import Form from './lib/Form.svelte';
  import Result from './lib/Result.svelte';
 
  let result = false;
  

  const handleThank = () => {
    result = true;
  };
</script>

    
    
  
<main>
  
  {#if result}
    <div><Result /></div>
  {:else}
    <div><Form callThanks={handleThank} /></div>
  {/if}
</main>
