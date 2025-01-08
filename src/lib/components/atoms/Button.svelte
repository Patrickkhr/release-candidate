<script>
  export let type;
  export let variant = "";
  export let size = "";
  export let href = "";
  export let title = "";
  export let icon = "";
  export let iconColor = "";
</script>

{#if href && variant === "primary"}
  <a
    {href}
    data-sveltekit-preload-data
    class="btn btn-primary btn-{size}"
    {...$$restProps}
  >
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </a>
{:else if href && variant === "secondary"}
  <a
    {href}
    data-sveltekit-preload-data
    class="btn btn-secondary btn-{size}"
    {...$$restProps}
  >
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </a>
{:else if href && variant === "tertiary"}
  <a
    {href}
    data-sveltekit-preload-data
    class="btn btn-tertiary btn-{size}"
    {...$$restProps}
  >
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </a>
{:else if variant === "primary"}
  <button {type} class="btn btn-primary btn-{size}" {...$$restProps} on:click>
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </button>
{:else if variant === "secondary"}
  <button {type} class="btn btn-secondary btn-{size}" {...$$restProps} on:click>
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </button>
{:else if variant === "tertiary"}
  <button {type} class="btn btn-tertiary btn-{size}" {...$$restProps} on:click>
    {title}
    {#if icon}
      <span class="btn-icon">
        <svelte:component this={icon} svgColor={iconColor} {...$$restProps} />
      </span>
    {/if}
    <slot></slot>
  </button>
{/if}

<style>
  .btn {
    display: flex;
    padding: 0.7em 1.5em 0.7em 1.5em;
    border-radius: 0.4em;
    align-items: center;
    vertical-align: middle;
    justify-content: center;
    text-align: center;
    line-height: var(--lh-1);
    text-decoration: none;
    padding: 0.7em 0.5em 0.7em 0.5em;
    gap: 0.5rem;
    border: 0;
    background-color: var(--bgc);
    color: var(--clr);
    border: var(--border);
    font-size: 14px;
    box-shadow: var(--box-shadow);
    cursor: pointer;
    transition:
      box-shadow 0.2s,
      transform 0.3s;
  }

  .btn:hover,
  .btn:focus {
    box-shadow: 0px 2px 3px 0px rgba(0, 0, 0, 0.25);
    transform: scale(1.1);
  }

  @media screen and (min-width: 768px) {
    .btn-secondary,
    .btn-tertiary {
      padding: 0.7em 1.5em 0.7em 1.5em;
    }
    .btn-tertiary .btn-icon {
      display: block;
    }
  }

  .btn-primary {
    border-radius: var(--btn-radius);
    background-color: var(--btn-primary-bg);
    color: var(--btn-primary-text-clr);
    box-shadow: var(--btn-shadow);
    border: 2px solid var(--btn-primary-bg);
    font-weight: 700;
  }

  .btn-secondary {
    border-radius: 0.4em;
    font-weight: 500;
    color: var(--page-bg-color);
    border: 1.5px solid var(--accent1-primary);
  }

  .btn-tertiary {
    background: var(--page-bg-color);
    color: var(--accent2-quaternary);
    justify-content: center;
  }

  .btn-secondary,
  .btn-primary {
    transition:
      box-shadow 0.2s,
      transform 0.3s;
  }

  .btn-icon {
    display: flex;
    align-items: center;
    width: 14px;
    height: 14px;
    transition: transform 0.3s ease;
  }

  .btn-tertiary .btn-icon {
    color: var(--txt-primary-clr);
  }

  .btn:hover .btn-icon,
  .btn:focus .btn-icon {
    transform: translateX(5px);
  }

  .btn-xs {
    --scale: 0.75;
    --btn-padding: 0.25em 0.75em;
  }

  .btn-sm {
    --scale: 0.875;
    --btn-padding: 0.375em 1em;
  }

  .btn-m {
    --scale: 0.975;
    --btn-padding: 0.8em 1em;
  }

  .btn-lg {
    --scale: 1.25;
    --btn-padding: 0.75em 1.5em;
  }

  .btn-xl {
    --scale: 1.5;
    --btn-padding: 1em 2em;
  }

  @media (min-width: 48em) {
    .btn-m {
      --scale: 1.5;
      --btn-padding: 0.8em 2em;
    }
  }
</style>
