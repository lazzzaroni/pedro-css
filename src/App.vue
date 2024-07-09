<script setup lang="ts">
import Pedro from "./components/Pedro.vue";
import Icon from "./components/Icon.vue";
</script>

<template>
  <div
    class="mx-auto flex h-svh min-w-0 max-w-5xl flex-auto flex-col justify-between p-4"
  >
    <header class="flex items-center justify-between">
      <div
        class="group mr-auto flex rounded-lg p-0.5 text-2xl tracking-tight hover_racoon"
      >
        <span class="font-extralight transition group-hover:-translate-x-0.5">
          PEDRO
        </span>
        <span class="font-semibold transition group-hover:translate-x-0.5">
          CSS
        </span>
      </div>
    </header>

    <main
      class="container mx-auto sm:px-6 lg:px-8 flex flex-col items-center gap-8"
    >
      <Pedro />
    </main>

    <footer className="flex text-sm mb-4">
      <div className="ml-auto flex items-center justify-end gap-4 md:px-2">
        <a
          href="https://github.com/lazzzaroni"
          target="_blank"
          rel="noopener noreferrer"
          className="rounded-md p-2 hover:bg-slate-800 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          aria-label="GitHub profile"
        >
          <Icon icon="GitHub" />
        </a>
        <a
          href="https://www.linkedin.com/in/mpaliakou/"
          target="_blank"
          rel="noopener noreferrer"
          className="rounded-md p-2 hover:bg-slate-800 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          aria-label="LinkedIn profile"
        >
          <Icon icon="LinkedIn" />
        </a>
        <a
          href="mailto:mpaliakou.dev@gmail.com"
          target="_self"
          className="rounded-md p-2 hover:bg-slate-800 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          aria-label="Email me"
        >
          <Icon icon="EnvelopeClosed" />
        </a>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.hover_racoon {
  cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='40' height='48' viewport='0 0 100 100' style='fill:black;font-size:24px;'><text y='50%'>🦝</text></svg>")
      0 16,
    auto;
}
</style>
