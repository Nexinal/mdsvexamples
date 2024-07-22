<svelte:options runes={true} />
<script lang="ts">
  import type { Snippet } from "svelte"
  
  let {
    src = undefined,
    meta =undefined,
    code,
    example
  } : {
    src: any | undefined,
    meta: any | undefined,
    code: Snippet,
    example:Snippet
  } = $props();

</script>

<div class="root">
  <div class="container">
    <div class="example-wrapper">
      <div class="example">
        {@render example?.()}
      </div>
    </div>
    <pre class="language-svelte">{@render code?.()}</pre>
  </div>
</div>

<style>
  .root {
    margin: 0.5rem 0;
  }

  .container {
    display: flex;
    flex-direction: column;
    width: 100%;
    overflow: hidden;
    border-bottom-left-radius: var(--example-border-radius, 0.25rem);
    border-bottom-right-radius: var(--example-border-radius, 0.25rem);
  }

  .example-wrapper {
    display: flex;
    justify-content: center;
    background: var(--example-background, #fafafa);
    border: var(--example-border, 1px solid #ddd);
    overflow: hidden;
    border-bottom: none;
    border-top-left-radius: var(--example-border-radius, 0.25rem);
    border-top-right-radius: var(--example-border-radius, 0.25rem);
  }

  .example {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0.75rem 0;
    min-height: 3rem;
  }

  pre {
    margin: 0;
  }
</style>
