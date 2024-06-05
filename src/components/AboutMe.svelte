<script lang="ts">
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
    { name: 'Duolingo', image: '', description: '' },
  ]
</script>

<style lang="scss">
  .about-me {
    height: 100vh;

    .hobbies {
      display: flex;
      margin: 35px 0;
      gap: 50px;

      .card {
        color: var(--colorBackground);
        height: 150px;
        width: 150px;
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

    <span>
      - Tengo muchos proyectos a medias porque muchas veces no me parece que estén quedando lo suficientemente bien y no se cómo continuar<br
      /><br />
      - Me considero una persona muy trabajadora pero si que es verdad que si carezco de objetivos claros me distraigo mucho<br /><br />
      - hay épocas en las que me descuido un poco a mí misma<br /><br />
      - Cuando estoy muy enfocada con algo a veces pierdo la noción del tiempo<br /><br />
      - Sigo buscando mi lugar en el mundo<br /><br />
      - A menudo me gomito encima<br /><br />
    </span>

    <p>
      Tengo poca experiencia en el mundo laboral pero ya he visto que la dinámica consiste en mostrar al mundo una versión perfecta y
      adulterada de uno mismo, escondiendo los defectos, exagerando la virtudes (O incluso inventando). <br /><br />
      Me expongo a quedar en peor lugar pero lo que estas viendo aqui es la Laia más humana y honesta, la que vas a ver todos los días.
    </p>
  </div>

  <div class="g-wrapper">
    <h2 class="title">Conoce lo mejor de mí</h2>

    <span>
      Soy una chica trabajadora y meticulosa con ganas de aprender. Mi entusiasmo y dedicación son activos valiosos para abordar
      eficientemente cualquier problema. Busco integrarme en un trabajo que valore el crecimiento mutuo, aportando una perspectiva fresca y
      soluciones efectivas.
    </span>

    <div class="hobbies">
      {#each hobbies as hobbie}
        <div class="card">{hobbie.name}</div>
      {/each}
    </div>
  </div>
</div>
