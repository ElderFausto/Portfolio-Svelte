<script>
  import { page } from "$app/stores";
  import Logo from "$lib/Logo.svelte";
  const items = [
    { href: "/", label: "Home" },
    { href: "/about", label: "About" },
    { href: "/projects", label: "Projects" },
    { href: "/contact", label: "Contact" },
  ];
</script>

<nav class="bg-white shadow dark:bg-gray-800">
  <div
    class="container flex items-center justify-center p-6 mx-auto text-gray-600 capitalize dark:text-gray-300"
  >
    <a href="/">
      <Logo />
    </a>

    {#each items as { href, label }}
      {#if $page.url.pathname === href}
        <a
          {href}
          class="text-gray-800 transition-colors duration-300 transform dark:text-gray-200 border-b-2 border-blue-500 mx-1.5 sm:mx-6"
          >{label}</a
        >
      {:else}
        <a
          {href}
          class="border-b-2 border-transparent hover:text-gray-800 transition-colors duration-300 transform dark:hover:text-gray-200 hover:border-blue-500 mx-1.5 sm:mx-6"
          >{label}</a
        >
      {/if}
    {/each}
  </div>
</nav>
