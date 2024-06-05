<script lang="ts">
  import Blobs from './Blobs.svelte'
  import SliderX from './generic-ui/SliderX.svelte'

  interface IHobbie {
    name: string
    image: string
    description: string
  }

  const hobbies: IHobbie[] = [
    { name: 'Programar', image: '', description: '' },
    { name: 'Diseñar', image: '', description: '' },
    { name: 'Leer', image: '', description: '' },
    { name: 'Videojuegos', image: '', description: '' },
    { name: 'Duolingo', image: 'https://blog.duolingo.com/content/images/2022/07/Duo_Trophy--1-.png', description: '' },
  ]
</script>

<style lang="scss">
  .g-wrapper {
    min-height: 100vh;
  }
  .about-me {
    height: fit-content;

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
        background-color: var(--colorBrand);
        font-weight: 500;
      }
    }
  }
</style>

<div class="about-me">
  <div class="g-wrapper">
    <h2 class="title">Conoce lo peor de mí</h2>
    <p>
      Tengo poca experiencia en el mundo laboral pero ya he visto que la dinámica consiste en mostrar al mundo una versión perfecta y
      adulterada de uno mismo, escondiendo los defectos, exagerando la virtudes (O incluso inventando). <br /><br />
      Me expongo a quedar en peor lugar pero lo que estas viendo aqui es la Laia más humana y honesta, la que vas a ver todos los días.
    </p>

    <Blobs />
  </div>

  <div class="g-wrapper">
    <h2 class="title">Conoce lo mejor de mí</h2>

    <p>
      Soy una chica trabajadora y meticulosa con ganas de aprender.<br /><br /> Mi entusiasmo y dedicación son activos valiosos para abordar
      eficientemente cualquier problema. <br /><br />Busco integrarme en un trabajo que valore el crecimiento mutuo, aportando una
      perspectiva fresca y soluciones efectivas.
    </p>

    <div class="hobbies">
      {#each hobbies as hobbie}
        <div class="card">
          <div class="name">{hobbie.name}</div>
          <img src="https://blog.duolingo.com/content/images/2022/07/Duo_Trophy--1-.png" alt="" />
        </div>
      {/each}
    </div>
  </div>
</div>
