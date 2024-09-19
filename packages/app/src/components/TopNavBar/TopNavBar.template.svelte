<script lang="ts">
  import { ConnectWalletButton } from '$components/Button';
  import { NavigationData, SocialsData } from '$configs';

  export let enableWalletConnect: boolean = true;
</script>

<div class="flex justify-between items-center container py-4 px-4">
  <!-- Left Section -->
  <div class="w-full">
    <slot name="logo">
      <a href="/" class="text-2xl">Title</a>
    </slot>
  </div>
  <!-- Middle Section -->
  <div class="flex items-center justify-center h-10 gap-4 lg:gap-8 body-bold">
    {#each NavigationData as data}
      <a href={data.url} class="w-fit">{data.label}</a>
    {/each}
  </div>

  <!-- Right Section -->
  <div class="lg:flex gap-2 lg:gap-8 items-center flex w-full justify-end">
    <!-- <ThemeToggle /> -->
    <div class="lg:flex gap-2 lg:gap-8 items-center flex">
      {#each SocialsData as data}
        {#if !data.disabled}
          <a href={data.url} class="w-fit">{data.label}</a>
        {/if}
      {/each}
    </div>
    {#if enableWalletConnect}
      <div class="hidden lg:flex">
        <ConnectWalletButton />
      </div>
    {/if}
  </div>
</div>
