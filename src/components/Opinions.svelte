<script lang="ts">
  import Svg from './Svg.svelte'

  export let text: string = ''
  export let author: string = ''
  export let title: string = ''
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .container {
    width: 100%;
    height: fit-content;
    position: relative;
    display: flex;
    justify-content: center;

    transform: scale(1.2);

    @include notDesktop {
      transform: scale(1);
    }

    .opinion {
      transition: 0.3s ease;
      height: fit-content;
      position: absolute;

      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 30px;

      .L-quote,
      .R-quote {
        opacity: 0.3;
        position: absolute;
        z-index: 1;
      }

      .L-quote {
        top: -20px;
        left: -40px;

        @include notDesktop {
          top: 0px;
          left: 20px;
        }
      }

      .R-quote {
        transform: scale(-1);
        bottom: -20px;
        right: -40px;

        @include notDesktop {
          right: 20px;
          bottom: 0px;
        }
      }

      .text {
        z-index: 2;
        font-size: 20px;
        text-wrap: balance;
        text-align: center;
        font-weight: bold;
      }

      .author {
        font-size: 14px;
        z-index: 2;
        margin-top: -25px;
        margin-right: -240px;
        color: var(--colorText2);
        cursor: default;

        @include notDesktop {
          margin-right: 0;
          font-size: 12px;
        }
      }
    }
  }
</style>

<div class="container">
  <div class="opinion">
    <div class="L-quote">
      <Svg name="quote" width="120" height="120" />
    </div>
    <div class="text">{text}</div>
    <div class="author" {title}>{author}</div>

    <div class="R-quote">
      <Svg name="quote" width="120" height="120" />
    </div>
  </div>
</div>
