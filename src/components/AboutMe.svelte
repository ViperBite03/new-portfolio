<script lang="ts">
  import Blobs from './Blobs.svelte'

  interface IHobbie {
    name: string
    image: string
    description: string
  }

  const hobbies: IHobbie[] = [
    { name: 'Programar', image: 'assets/code.png', description: '' },
    { name: 'Diseñar', image: 'assets/brush.png', description: '' },
    {
      name: 'Leer',
      image: 'assets/book.png',
      description: '',
    },
    { name: 'Videojuegos', image: 'assets/controller.png', description: '' },
    { name: 'Duolingo', image: 'assets/duolingo.png', description: '' },
    {
      name: 'Escuchar música',
      image: 'assets/headphone.png',
      description: '',
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

    .worst {
      height: 100dvh;
      margin: 0 auto;

      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .best {
      height: 100dvh;
    }

    .soft {
      font-size: 16px;
      color: var(--colorText3);
    }

    .hobbies {
      display: flex;
      width: 100%;
      margin: 35px 0;
      justify-content: space-between;

      .card {
        color: var(--colorBackground);
        height: 175px;
        width: 175px;
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

<div class="about-me">
  <div class="worst">
    <div class="text g-wrapper">
      <h2 class="title">Conoce lo peor de mí</h2>
      <p>
        Tengo poca experiencia en el mundo laboral, pero ya he visto que la dinámica consiste en mostrar al mundo una versión perfecta y
        adulterada de uno mismo, escondiendo los defectos o exagerando la virtudes <span class="soft">(incluso inventando)</span>. <br /><br
        />
        Me expongo a quedar en mal lugar, pero lo que estas viendo aquí es la Laia más humana y honesta, la que vas a ver todos los días.
      </p>
    </div>

    <Blobs />
  </div>

  <div class="best g-wrapper">
    <h2 class="title">Conoce lo mejor de mí</h2>

    <p>
      A parte de defectos también tengo virtudes <span class="soft">(sino qué gracia tendría todo esto, no?)</span> y aunque me guste hablar
      de lo malo, a todo se le puede sacar algo bueno. <br /><br /> Soy meticulosa y perfeccionista, soy atenta y por mucho que me guste
      divagar, tambien me gusta hacer las cosas bien y rápido.<br /><br />Estos son algunos de mis hobbies, para que me conozcas más:<br
      /><br /><br />
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
