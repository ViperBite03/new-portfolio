<script lang="ts">
  interface IStudy {
    name: string
    date: string
    description: string
  }

  const studies: IStudy[] = [
    {
      name: 'Titulación oficial de lengua inglesa',
      date: 'Algún momento del 2018',
      description: 'Título C1 Advanced',

      /*C1 Advanced is used for study, work and immigration purposes.
      It is designed to demonstrate that a candidate has achieved a high level
      of English ability which can be used in academic and professional contexts.*/
    },
    {
      name: 'Educación Secundaria (Bachillerato tecnológico)',
      date: '2019 - 2022',
      description: 'IES Palau Ausit, Ripollet',
    },

    {
      name: 'Algún que otro curso en LinkedIn',
      date: 'Actualidad',
      description: 'Se le puede sacar provecho a cualquier cosa, desde cursos de YouTube hasta de LinkedIn',
    },
    {
      name: 'Ingeniería de Sistemas Audiovisuales',
      date: '2022 - 2024',
      description: 'Universidad politécnica de Cataluña (UPC - ESEIAAT)',
    },
    {
      name: 'Japonés en Duolingo',
      date: 'Racha de 180 días',
      description: 'Tres minutos al día hacen 1095 minutos al año, que es más que nada',
    },
  ]
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  .studies {
    min-height: 100dvh;
    display: flex;
    flex-direction: column;
    gap: 50px;

    .container {
      display: flex;
      flex-direction: column;
      gap: 30px;

      .experience {
        display: flex;
        //align-items: center;
        gap: 20px;
        transform: scale(1.1);
        margin: 0 15px;

        .index {
          height: 40px;
          width: 40px;
          border: 1px solid var(--colorBrand);
          color: var(--colorBrand);
          border-radius: 100%;
          font-size: 18px;

          flex-shrink: 0;

          display: flex;
          align-items: center;
          justify-content: center;
        }

        .content {
          display: flex;
          flex-direction: column;
        }
      }
    }
  }
</style>

<div id="studies" class="studies g-wrapper">
  <h2 class="title">Formación</h2>

  <div class="container">
    {#each studies as study, i}
      <div class="experience">
        <div class="index">{i + 1}</div>
        <div class="content">
          <span class="name" style="font-weight: bolder; font-size: 18px;">{study.name}</span>
          <span class="date" style="color: var(--colorText3);">{study.date}</span>
          <span class="description">{study.description}</span>
        </div>
      </div>
    {/each}
  </div>
</div>
