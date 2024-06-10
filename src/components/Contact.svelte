<script lang="ts">
  import Svg from './Svg.svelte'

  let show: boolean = false

  const copy = () => {
    navigator.clipboard.writeText('lamadelafu03@gmail.com')

    show = true
    setTimeout(() => (show = false), 1000)
  }
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  @include notDesktop {
    h2 {
      font-size: 35px !important;
    }
  }
  .contact {
    height: 100dvh;
    display: flex;
    flex-direction: column;

    .links {
      display: flex;
      flex-direction: column;
      width: fit-content;
      height: 100%;
      gap: 20px;
      margin-top: 75px;

      .mail {
        display: flex;
        gap: 20px;
      }

      .link {
        width: fit-content;

        .name {
          text-align: left;
          font-size: 25px;
          font-weight: bold;
          transition: 0.3s ease;

          &:hover {
            color: var(--colorBrand);
            transition: 0.3s ease;
          }

          @include notDesktop {
            max-width: 310px;
          }
        }
      }

      .icons {
        display: flex;
        align-items: center;

        .icon {
          transition: 0.3s ease;

          &:hover {
            :global(svg) {
              fill: var(--colorBrand);
              transition: 0.3s ease;
            }
          }
        }
      }

      .mail {
        display: flex;
        position: relative;

        .copied {
          width: fit-content;
          height: fit-content;
          display: flex;
          align-items: center;
          opacity: 0;
          cursor: default;
          transition: 0.3s ease;

          &.show {
            opacity: 0.4;
            transition: 0.3s ease;
          }

          .triangle {
            height: 15px;
            width: 15px;

            clip-path: polygon(0 50%, 100% 100%, 100% 0);
            background-color: black;
            margin-right: -1px;
          }

          .square {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 8px;
            border-radius: 8px;

            background-color: black;
            font-size: 13px;
          }

          @include notDesktop {
            flex-direction: column-reverse;
            position: absolute;

            top: -55px;
            left: 35px;

            .triangle {
              clip-path: polygon(50% 100%, 0 0, 100% 0);
            }
          }
        }
      }
    }
  }
</style>

<div class="contact g-wrapper">
  <h2 class="title">¿Alguna duda? Hablemos</h2>

  <div class="links">
    <div class="mail">
      <button class="link" on:click={copy}>
        <div class="name">Mándame un email</div>
      </button>

      <div class="copied" class:show>
        <div class="triangle"></div>
        <div class="square">Copiado al portapapeles</div>
      </div>
    </div>

    <a href="https://wa.me/+34671707263" class="link">
      <div class="name">Háblame por WhatsApp</div>
    </a>

    <a href="assets/CV_LaiaMartin.pdf" class="link" download>
      <div class="name">
        Descarga mi currículum <span style="font-size: 16px; color: var(--colorText3);">(por si no lo habias visto aún)</span>
      </div>
    </a>

    <div class="icons">
      <a href="https://github.com/ViperBite03" title="GitHub" class="icon">
        <Svg name="github" height="50" width="50" />
      </a>

      <a href="https://www.linkedin.com/in/laia-martin-de-la-fuente-660031280/" title="LinkedIn" class="icon">
        <Svg name="linkedin" height="50" width="50" />
      </a>

      <!--<a href="https://wa.me/671707263" title="WhatsApp" class="icon">
        <Svg name="whatsapp" height="45" width="45" />
      </a>-->
    </div>
  </div>
</div>
