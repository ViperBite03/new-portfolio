<script lang="ts">
  import Slider from './Slider.svelte'

  const blobs = [
    {
      svg: `
        <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
            <path d="M38,-30.6C48.6,-17,56.1,-1.2,54.1,14.3C52.1,29.9,40.7,45.2,25.8,51.7C10.9,58.2,-7.4,55.8,-26.4,48.9C-45.3,42,-64.9,30.7,-67.6,16.2C-70.3,1.7,-56.1,-15.8,-42,-30.2C-27.9,-44.6,-13.9,-55.8,-0.1,-55.7C13.7,-55.6,27.4,-44.2,38,-30.6Z" transform="translate(100 100)" />
        </svg>
      `,

      title: 'Bloqueo',
      text: 'Muchas veces los resultados no me parecen lo suficientemente buenos y no se cómo continuar',
    },
    {
      svg: `
      <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path d="M43.9,-48.3C59.3,-39.5,75.8,-27.9,82.1,-11.6C88.4,4.6,84.4,25.5,73.9,41.6C63.3,57.6,46.2,68.8,29,71.6C11.8,74.3,-5.6,68.7,-24.2,63.3C-42.8,57.9,-62.7,52.8,-70.5,40.3C-78.2,27.7,-73.8,7.7,-66.3,-7.7C-58.8,-23.1,-48.1,-33.9,-36.6,-43.4C-25,-53,-12.5,-61.3,0.9,-62.4C14.3,-63.4,28.6,-57.2,43.9,-48.3Z" transform="translate(100 100)" />
      </svg>
      `,

      title: 'Distracción',
      text: 'Si carezco de objetivos claros<br> tiendo a divagar',
    },
    {
      svg: `
      <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path d="M50,-55.3C66,-46.1,81.1,-31.5,81.2,-16.5C81.4,-1.4,66.5,14.2,54.6,28.5C42.8,42.7,33.8,55.6,20.6,63.5C7.3,71.3,-10.4,74.2,-25.9,69.4C-41.4,64.5,-54.8,51.9,-63.3,36.8C-71.7,21.6,-75.2,3.9,-71.6,-11.9C-67.9,-27.6,-57.1,-41.4,-43.9,-51C-30.8,-60.7,-15.4,-66.3,0.8,-67.3C17,-68.2,33.9,-64.4,50,-55.3Z" transform="translate(100 100)" />
      </svg>
      `,

      title: 'Sentido',
      text: 'Sigo buscando<br> mi lugar en el mundo',
    },
    {
      svg: `
      <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path d="M39.4,-55C53.7,-43.9,69.6,-35.8,71.3,-24.6C73,-13.4,60.4,1.1,52.2,14.1C44.1,27.2,40.4,38.8,32.4,46.3C24.4,53.8,12.2,57.2,-0.1,57.4C-12.4,57.5,-24.8,54.3,-40.1,49.2C-55.4,44.1,-73.6,37,-78.8,24.7C-84.1,12.5,-76.3,-4.9,-66.9,-18C-57.5,-31.1,-46.5,-40,-35.1,-52C-23.6,-64.1,-11.8,-79.4,0.4,-79.9C12.6,-80.4,25.2,-66.2,39.4,-55Z" transform="translate(100 100)" />
      </svg>
      `,

      title: 'Abandono',
      text: 'Hay épocas en las que me <br> descuido un poco a mí misma',
    },
    {
      svg: `<svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path d="M31.1,-53.7C40.3,-42.4,47.7,-33.8,52.3,-23.9C56.9,-13.9,58.6,-2.6,57.2,8.4C55.9,19.4,51.6,30.2,45.6,42.7C39.7,55.3,32.2,69.7,20.6,75.5C9,81.3,-6.6,78.6,-19.5,72.2C-32.5,65.8,-42.7,55.9,-55,45.5C-67.3,35.2,-81.7,24.5,-85.6,11C-89.6,-2.4,-83,-18.7,-73.7,-31.3C-64.3,-44,-52.1,-53,-39.3,-62.7C-26.6,-72.3,-13.3,-82.7,-1.2,-80.8C10.9,-79,21.9,-65,31.1,-53.7Z" transform="translate(100 100)" />
    </svg>`,

      title: 'Obsesión',
      text: 'Cuando estoy muy enfocada <br> con algo suelo perder la <br>noción del tiempo',
    },
  ]
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  .blobs {
    display: flex;
    padding-top: 70px;
    gap: 20px;
    align-items: center;
    overflow-y: hidden;

    .blob {
      position: relative;
      display: flex;
      flex-direction: column;
      gap: 20px;
      align-items: center;
      justify-content: center;
      width: 350px;
      height: 300px;

      h3 {
        text-align: center;
        font-size: 25px;
        font-weight: bold;
      }

      p {
        text-align: center;
        width: 300px;
        text-wrap: pretty;
        font-size: 16px;
        min-height: 100px;
      }

      :global(svg) {
        position: absolute;
        width: 100%;
        height: 100%;
        z-index: -1;
        fill: var(--colorBrand);
        opacity: 0.6;
        animation-name: move;
        animation-duration: 60s;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
      }

      @keyframes move {
        0% {
          transform: rotate(0);
        }
        100% {
          transform: rotate(360deg);
        }
      }
    }
  }
</style>

<div class="blobs">
  {#if window.innerWidth < 1070}
    <Slider>
      {#each blobs as blob}
        <div class="blob">
          <h3>{blob.title}</h3>
          <p>
            {@html blob.text}
          </p>
          {@html blob.svg}
        </div>
      {/each}
    </Slider>
  {:else}
    {#each blobs as blob}
      <div class="blob">
        <h3>{blob.title}</h3>
        <p>
          {@html blob.text}
        </p>
        {@html blob.svg}
      </div>
    {/each}
  {/if}
</div>
