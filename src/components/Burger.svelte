<script lang="ts">
  export let active: boolean = false
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .burger {
    position: absolute;
    width: 32px;
    height: 24px;
    cursor: pointer;
    right: 20px;
    z-index: 20;

    @include desktop {
      display: none;
    }
  }

  .burger span {
    width: 100%;
    height: 4px;
    background-color: var(--colorBrand);
    border-radius: 12px;
    display: block;
    transition: background-color 0.5s ease-in-out;
  }

  .burger span::before,
  .burger span::after {
    content: '';
    width: 100%;
    background-color: var(--colorBrand);
    display: block;
    transition: all 0.5s ease-in-out;
    border-radius: 12px;
    height: 4px;
  }

  .burger span::before {
    transform: translateY(-10px);
  }

  .burger span::after {
    transform: translateY(10px);
    margin-top: -4px;
  }

  .burger.active span {
    background-color: transparent;
  }

  .burger.active span::before {
    transform: rotateZ(45deg) translateY(0);
  }

  .burger.active span::after {
    transform: rotateZ(-45deg) translateY(0);
  }
</style>

<button class="burger" class:active on:click={() => (active = !active)}>
  <span></span>
</button>
