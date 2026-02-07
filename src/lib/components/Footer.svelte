<script lang="ts">
  import { resolve } from "$app/paths";
  import { page } from "$app/state";
  import { cn } from "$lib/utils";

  const url = $derived(page.url.pathname);
</script>

<footer class="p-4 text-center text-accent">
  <div class="mb-2 flex justify-center divide-x divide-accent">
    <a
      href="https://tonantzintla.org"
      target="_blank"
      rel="noopener"
      class="px-4 underline-offset-2 transition-colors duration-300 hover:text-muted-foreground"
      >Tonantzintla</a>
    <a
      href={resolve("/[slug]", { slug: "privacy-policy" })}
      class={cn(
        "px-4 underline-offset-2 transition-colors duration-300 hover:text-muted-foreground",
        { underline: url === "/privacy-policy" }
      )}>Privacy Policy</a>
    <a
      href={resolve("/[slug]", { slug: "terms-of-service" })}
      class={cn(
        "px-4 underline-offset-2 transition-colors duration-300 hover:text-muted-foreground",
        { underline: url === "/terms-of-service" }
      )}>Terms of Service</a>
  </div>
  &copy; {new Date().getFullYear()} Tonantzintla. All rights reserved.
</footer>
