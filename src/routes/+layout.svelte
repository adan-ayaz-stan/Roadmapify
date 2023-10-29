<script>
  import "./styles.css";
  import { page } from "$app/stores";

  import Icon from "@iconify/svelte";
  import { Button } from "$lib/components/ui/button";

  $: activeUrl = $page.url.pathname;
  let data = [
    {
      title: "Home",
      link: "/",
    },
    {
      title: "About",
      link: "/about",
    },
    {
      title: "Contact",
      link: "/contact",
    },
    {
      title: "Privacy",
      link: "/privacy",
    },
  ];

  import { onMount } from "svelte";
  import { browser } from "$app/environment";

  let prevScrollPos;
  let isScrollingDown = false;

  function handleScroll() {
    const currentScrollPos =
      window.pageYOffset || document.documentElement.scrollTop;
    isScrollingDown = currentScrollPos > prevScrollPos;
    prevScrollPos = currentScrollPos;
  }

  onMount(() => {
    prevScrollPos = window.pageYOffset || document.documentElement.scrollTop;
    if (browser) {
      window.addEventListener("scroll", handleScroll);
    }
  });
</script>

<div class="app">
  <div
    class="fixed top-0 w-full flex flex-row justify-between items-center py-4 px-4 md:px-8 lg:px-20 bg-white transition-all duration-500 z-10"
    style={isScrollingDown
      ? "transform: translateY(-100%);"
      : "transform: translateY(0%)"}
  >
    <div class="flex flex-row gap-3 items-center">
      <img src="/logo/logo-black.svg" alt="company-logo" class="h-16" />
      <h1
        style="font-family: 'Roboto Slab', serif;"
        class="font-semibold uppercase tracking-wider text-3xl"
      >
        Roadmapify
      </h1>
    </div>

    <div class="flex flex-row gap-3">
      {#each data as item (item.link)}
        <a href={item.link}>
          <Button
            type={"button"}
            class="text-black py-0 pl-1 bg-white border-[1px] border-gray-300 rounded-full hover:border-gray-500 hover:bg-white"
          >
            {#if activeUrl == item.link}
              <Icon icon="radix-icons:dot-filled" width="24" height="24" />
            {:else}
              <Icon icon="radix-icons:dot" width="24" height="24" />
            {/if}
            {item.title}
          </Button>
        </a>
      {/each}
    </div>
  </div>
  <main>
    <slot />
  </main>
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    width: 100%;
    /* max-width: 64rem; */
    margin: 0 auto;
    box-sizing: border-box;
  }
</style>
