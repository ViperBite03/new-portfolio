<script lang="ts">
  import Blobs from './Blobs.svelte'

  interface IHobbie {
    name: string
    image: string
  }

  const hobbies: IHobbie[] = [
    { name: 'Programar', image: 'assets/code.png' },
    { name: 'Diseñar', image: 'assets/brush.png' },
    {
      name: 'Leer',
      image: 'assets/book.png',
    },
    { name: 'Videojuegos', image: 'assets/controller.png' },
    /*{ name: 'Duolingo', image: 'assets/duolingo.png' },*/
    {
      name: 'Escuchar música',
      image: 'assets/headphone.png',
    },
  ]
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  .g-wrapper {
    display: flex;
    flex-direction: column;
  }

  .about-me {
    height: fit-content;
    display: flex;
    flex-direction: column;
    gap: 150px;

    .worst {
      min-height: 100dvh;

      display: flex;
      flex-direction: column;
    }

    .best {
      min-height: 100dvh;
    }

    .soft {
      font-size: 16px;
      color: var(--colorText3);
    }

    .hobbies {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      justify-content: space-between;
      gap: 20px;
      width: 100%;
      margin: 35px 0;

      .card {
        color: var(--colorBackground);
        height: 175px;
        width: 100%;
        padding: 20px;
        border-radius: 20px;
        background-color: rgba(144, 126, 255, 0.6);
        font-weight: 500;
        font-size: 20px;
        position: relative;

        .image {
          height: 100px;
          opacity: 0.3;
          position: absolute;
          filter: brightness(0);

          bottom: 10px;
          right: 10px;
        }
      }
    }
  }
</style>

<div id="aboutme" class="about-me">
  <div class="worst">
    <div class="text g-wrapper">
      <h2 class="title">Conoce lo peor de mí</h2>
      <p>
        Tengo poca experiencia en el mundo laboral, pero ya he visto que la dinámica consiste en mostrar al mundo una versión perfecta y
        adulterada de uno mismo, escondiendo los defectos o exagerando las virtudes <span class="soft">(incluso inventando)</span>.
        <br /><br />
        Me expongo a quedar en mal lugar, pero lo que estas viendo aquí es la Laia más humana y honesta, la que vas a ver todos los días.
      </p>
    </div>

    <Blobs />
  </div>

  <div class="best g-wrapper">
    <h2 class="title">Conoce lo mejor de mí</h2>

    <p>
      A parte de defectos también tengo virtudes <span class="soft">(sino qué gracia tendría todo esto, no?)</span> y aunque me guste hablar
      de lo malo, a todo se le puede sacar algo bueno. <br /><br /> Soy proactiva y curiosa, lo que me ha facilitado aprender muchas cosas
      de forma autodidácta, no paro quieta así que tengo mil hobbies, estos son algunos de ellos:<br /><br /><br />
    </p>

    <div class="hobbies">
      {#each hobbies as hobbie}
        <div class="card">
          <div class="name">{hobbie.name}</div>
          <img src={hobbie.image} alt="" class="image" />
        </div>
      {/each}
    </div>
  </div>
</div>
