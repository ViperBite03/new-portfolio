<script lang="ts">
  import { onMount } from 'svelte'

  export let itemWidth: number = 350
  export let gap: string = '0'

  let HTMLslides: HTMLElement
  let index: number = 0
  let onMounted: boolean = false

  $: if (HTMLslides) HTMLslides.style.transform = `translateX(${itemWidth * index}px)`

  onMount(() => {
    const nItems: number =
      HTMLslides.children[0].nodeName === 'ASTRO-SLOT' ? HTMLslides.children[0].children.length : HTMLslides.children.length

    HTMLslides.style.width = `${nItems * itemWidth}px`

    onMounted = true
  })
</script>

<style lang="scss">
  @import '../sass/mixins.scss';

  .container-slider {
    margin: auto;
    width: 100%;

    .slider-x {
      height: fit-content;
      overflow-x: auto;
      overflow-y: hidden;
      opacity: 0;

      @include desktop {
        display: flex;
        justify-content: center;
      }

      &.onMounted {
        transition: 0.3s ease;
        opacity: 1;
      }

      &::-webkit-scrollbar {
        display: none;
      }

      .slides {
        display: flex;
        transition: 0.3s ease-in-out;
        padding: 10px 0;
      }
    }
  }
</style>

<div class="container-slider">
  <div class="slider-x" class:onMounted>
    <div class="slides" bind:this={HTMLslides} style:gap={gap + 'px'}>
      <slot />
    </div>
  </div>
</div>
