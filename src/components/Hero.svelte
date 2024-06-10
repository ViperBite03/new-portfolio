<script lang="ts">
  import Svg from './Svg.svelte'
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  .hero {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100dvh;

    .message {
      display: flex;
      flex-direction: column;
      align-items: center;

      width: 1000px;

      .bait {
        font-size: 70px;
        font-weight: bolder;

        @include notDesktop {
          font-size: 30px;
        }
      }

      h1 {
        padding-top: 50px;
        padding-bottom: 25px;
        font-size: 28px;
        text-align: center;

        @include notDesktop {
          font-size: 20px;
        }
      }

      h3 {
        font-size: 28px;
        @include notDesktop {
          font-size: 20px;
        }
      }
    }

    :global(.scroll-down) {
      position: absolute;
      bottom: 20px;
      left: 0;
      right: 0;
      margin: auto;
    }

    :global(.puntito) {
      animation-name: down;
      animation-duration: 2s;
      animation-iteration-count: infinite;
      transition-timing-function: cubic-bezier(1, -0.585, 0.31, 1.65);
    }

    @keyframes down {
      0% {
        opacity: 0;
        transform: translateY(0);
      }
      20% {
        opacity: 1;
      }
      90% {
        opacity: 1;
      }
      100% {
        transform: translateY(150px);
        opacity: 0;
      }
    }
  }
</style>

<div class="hero g-wrapper">
  <div class="message">
    <h2 class="bait color" reveal>¿Qué haces aquí?</h2>

    <h1 reveal="0.6">
      ¿Mi perfil te ha llamado la atención y quieres saber más <br /> o no tienes idea de quien soy ni de que va esta web?
    </h1>

    <h3 reveal="0.9">En cualquier caso, <span class="color">sigue leyendo.</span></h3>
  </div>

  <Svg name="scroll" width="80" height="80" className="scroll-down" />
</div>
