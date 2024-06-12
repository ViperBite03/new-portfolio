<script lang="ts">
  import { onMount } from 'svelte'
  import Burger from '@/components/Burger.svelte'

  let slim: boolean = false
  let active: boolean = false

  onMount(() => {
    window.addEventListener('scroll', () => {
      slim = window.scrollY > 10
    })
  })

  const items = [
    {
      title: 'Sobre mí',
      elem: document.querySelector('#about-me'),
    },
    {
      title: 'Formación',
      elem: document.querySelector('#studies'),
    },
    {
      title: 'Experiencia',
      elem: document.querySelector('#career'),
    },
    {
      title: 'Contacto',
      elem: document.querySelector('#contact'),
    },
  ]

  const scrollTo = (elem: Element) => {
    elem.scrollIntoView({ behavior: 'smooth' })
    active = false
  }

  onMount(() => {
    function callback(entries: IntersectionObserverEntry[], observer: IntersectionObserver): void {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          console.log('Elemento visible', entry.target.id)
        }
      })
    }

    const options = {
      root: null,
      rootMargin: '0px',
      threshold: 0.5,
    }

    const observer = new IntersectionObserver(callback, options)

    console.log('hola')

    for (let item of items) observer.observe(item.elem)
  })

  //$: document.body.style.overflow = active ? 'hidden' : 'auto'
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .navbar-container {
    position: fixed;
    width: 100%;
    max-height: 100px;
    z-index: 10;

    backdrop-filter: blur(10px);
    overflow: hidden;

    &.active {
      max-height: 100%;
    }

    .top-bar {
      transition: 0.3s ease;
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100px;
      padding: 15px;

      &.slim {
        transition: 0.3s ease;
        height: 70px;
        border-bottom: 1px solid transparent;
        background-color: rgba(0, 0, 0, 0.5);

        @include desktop {
          border-bottom: 1px solid var(--colorBrand);
        }
      }

      @include notDesktop {
        height: 70px;
        border-bottom: 1px solid var(--colorBrand) !important;
      }
    }

    &.active {
      height: 100dvh;
    }

    img {
      height: 100%;
      max-height: 80px;
    }

    .right-items {
      padding-right: 10px;
      display: flex;

      button {
        transition: 0.3s ease;
        cursor: pointer;
        padding: 30px;

        &:hover {
          color: var(--colorBrand);
        }
      }
    }

    .burger-items {
      transition: 0.3s ease;
      display: none;
      position: fixed;
      width: 100%;
      z-index: 10;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      background-color: rgba(0, 0, 0, 0.5);

      height: calc(100dvh);

      button {
        padding: 20px;
        width: 100%;
        text-align: center;
        font-size: 30px;
      }
    }

    @include notDesktop {
      .right-items {
        display: none;
      }

      .burger-items {
        display: flex;
      }
    }
  }
</style>

<div class="navbar-container" class:active>
  <div class="top-bar" class:slim>
    <img src="/assets/laiamartin.png" alt="Laia Martin" />

    <div class="right-items">
      {#each items as item}
        <button on:click={() => scrollTo(item.elem)}> {item.title}</button>
      {/each}
    </div>

    <Burger bind:active />
  </div>

  <div class="burger-items" class:slim>
    {#each items as item}
      <button on:click={() => scrollTo(item.elem)}> {item.title}</button>
    {/each}
  </div>
</div>
