<script lang="ts">
  interface IStudy {
    name: string
    date: string
    description: string
  }

  const studies: IStudy[] = [
    {
      name: 'Ingeniería de Sistemas Audiovisuales',
      date: '2022 - 2024',
      description: 'Universidad politécnica de Cataluña (UPC - ESEIAAT)',
    },
    {
      name: 'Algún que otro curso en LinkeIn',
      date: '2024',
      description: 'Se le puede sacar provecho a cualquier cosa, desde cursos en YouTube hasta homologados por LinkedIn',
    },
    {
      name: 'Educación Secundaria (Bachillerato)',
      date: '2019 - 2022',
      description: 'IES Palau Ausit, Ripollet',
    },
    {
      name: 'Titulación oficial de lengua inglesa',
      date: 'Agosto 2022',
      description: 'Título C1 Advanced',

      /*C1 Advanced is used for study, work and immigration purposes.
      It is designed to demonstrate that a candidate has achieved a high level
      of English ability which can be used in academic and professional contexts.*/
    },
    {
      name: 'Japonés en Duolingo',
      date: 'Racha de 170 días',
      description: 'Tres minutos al día hacen 1095 minutos al año',
    },
  ]
</script>

<style lang="scss">
  .studies {
    height: 100vh;
  }
</style>

<div class="studies g-wrapper">
  <h2 class="title">Formación</h2>

  <div class="studies">
    {#each studies as study}
      <div class="experience">
        <span class="name">{study.name}</span>
        <span class="date">{study.date}</span>
        <span class="description">{study.description}</span>
      </div>
    {/each}
  </div>
</div>
