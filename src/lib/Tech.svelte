<script lang="ts">
  import { slide, fade } from 'svelte/transition'
  import Skills from './Tech.Skills.svelte'
  import FaAngleDown from 'svelte-icons/fa/FaAngleDown.svelte'

  let isDisclosureOpen = false
  function handleOpenDisclosure() {
    isDisclosureOpen = !isDisclosureOpen
  }
</script>

<section>
  <div class="flex flex-col justify-center items-center">
    <h2
      class="text-2xl text-blue-700 text-opacity-90 font-bold uppercase mb-4 select-none"
    >
      Tecnologias
    </h2>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div
      on:click={handleOpenDisclosure}
      class="flex justify-between items-center w-full mb-8 px-2 rounded-lg transition-all ease-out hover:bg-slate-300"
    >
      <span class="inline-flex w-[90%] h-[0.10rem] bg-slate-500" />
      <div class="inline-flex w-4 h-4 text-slate-800">
        <FaAngleDown />
      </div>
    </div>
    {#if isDisclosureOpen}
      <div class="w-full" in:fade out:slide={{ duration: 500 }}>
        <Skills />
      </div>
    {/if}
  </div>
</section>
