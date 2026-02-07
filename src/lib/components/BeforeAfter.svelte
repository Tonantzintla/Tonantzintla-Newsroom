<script lang="ts">
  import * as Tabs from "$lib/components/ui/tabs";
  import { getMediaType } from "$lib/utilities";
  import { cubicInOut } from "svelte/easing";
  import { crossfade } from "svelte/transition";

  const { before, after }: { before: string; after: string } = $props();

  let value = $state("before");

  const tabs = [
    { title: "Before", value: "before" },
    { title: "After", value: "after" },
  ];

  const [send, receive] = crossfade({
    duration: 300,
    easing: cubicInOut,
  });
</script>

<Tabs.Root
  bind:value
  class="flex h-120 shrink flex-col justify-between rounded-lg border border-border bg-popover p-4">
  <Tabs.List class="mx-auto bg-secondary">
    {#each tabs as tab, index (index)}
      {@const isActive = value === tab.value}
      <Tabs.Trigger
        value={tab.value}
        class="relative text-secondary-foreground transition-colors duration-300 data-[state=active]:bg-transparent data-[state=active]:text-primary-foreground"
        data-sveltekit-noscroll>
        {#if isActive}
          <div
            class="absolute inset-0 rounded-sm bg-primary"
            in:send={{ key: "active-tab" }}
            out:receive={{ key: "active-tab" }}>
          </div>
        {/if}
        <div class="relative">
          {tab.title}
        </div>
      </Tabs.Trigger>
    {/each}
  </Tabs.List>
  <Tabs.Content value="before" class="h-full">
    <div class="flex h-full items-center">
      {#if getMediaType(before) === "image"}
        <img
          in:send={{ key: "active-image" }}
          out:receive={{ key: "active-image" }}
          src={before}
          class="pointer-events-none m-0 mx-auto max-h-98 rounded-lg object-contain"
          alt="Before" />
      {:else if getMediaType(before) === "video"}
        <video
          class="pointer-events-none m-0 mx-auto max-h-98 rounded-lg"
          autoPlay={true}
          muted={true}
          loop={true}>
          <source src={before} type={`video/${before.split(".").pop()}`} />
        </video>
      {:else}
        <p>Unsupported media type</p>
      {/if}
    </div>
  </Tabs.Content>
  <Tabs.Content value="after" class="h-full">
    <div class="flex h-full items-center">
      {#if getMediaType(after) === "image"}
        <img
          src={after}
          class="pointer-events-none m-0 mx-auto max-h-98 rounded-lg object-contain"
          alt="After" />
      {:else if getMediaType(after) === "video"}
        <video
          class="pointer-events-none m-0 mx-auto max-h-98 rounded-lg"
          autoPlay={true}
          muted={true}
          loop={true}>
          <source src={after} type={`video/${after.split(".").pop()}`} />
        </video>
      {:else}
        <p>Unsupported media type</p>
      {/if}
    </div>
  </Tabs.Content>
</Tabs.Root>
