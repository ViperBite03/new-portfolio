<script lang="ts">
  interface IExperience {
    name: string
    date: string
    description: string
  }

  const experiences: IExperience[] = [
    {
      name: 'Pequeña dependienta de una pequeña tienda',
      date: 'Agosto 2022',
      description: 'El verano de 2022 trabajé de forma temporal como dependienta de tienda en Valladolid',
    },
    {
      name: 'Camarera navideña',
      date: 'Diciembre 2023 - enero 2024',
      description: 'Trabajé durante la temporada navideña en La Massamara (Ripollet)',
    },
    {
      name: 'Teleoperadora',
      date: 'Enero 2024 - abril 2024',
      description: 'Sector energético',
    },
    {
      name: 'Inserte nombre de tu negocio',
      date: 'Incorporación inmediata',
      description: 'Hueco vacío esperando a ser rellenado',
    },
  ]
</script>

<style lang="scss">
  .experiences {
    width: 100%;
    height: 75vh;
    display: flex;
    gap: 50px;

    .experience {
      display: flex;
      flex-direction: column;
      text-align: justify;
      padding: 20px;

      max-width: 300px;
      max-height: 300px;

      .name {
        font-size: 25px;
        font-weight: bolder;
      }

      .date {
        color: var(--colorText3);
        margin-bottom: 10px;
      }

      &.active {
        opacity: 0.5;
        border: 1px solid var(--colorText);
        border-style: dashed;
      }
    }
  }
</style>

<div class="career g-wrapper">
  <h2 class="title">Experiencia</h2>

  <div class="experiences">
    {#each experiences as experience, i}
      <div class="experience" class:active={i === 3}>
        <span class="name">{experience.name}</span>
        <span class="date">{experience.date}</span>
        <span class="description">{experience.description}</span>
      </div>
    {/each}
  </div>
</div>
