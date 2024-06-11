<script lang="ts">
  import Opinions from './Opinions.svelte'

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
      description: 'Estuve como teleoperadora en una compañía del sector energético como vendedora telefónica.',
    },
    {
      name: 'Inserte nombre de su negocio',
      date: 'Incorporación inmediata',
      description: 'Hueco vacío esperando a ser rellenado',
    },
  ]
</script>

<style lang="scss">
  @import './../sass/mixins.scss';

  .g-wrapper {
    padding: 20px 30px;
  }

  .career {
    min-height: 100dvh;
    width: 100%;

    display: flex;
    flex-direction: column;
    gap: 100px;

    @include notDesktop {
      gap: 35px;
    }

    .experiences {
      display: flex;
      justify-content: center;
      width: 100%;
      margin-bottom: 125px;
      gap: 50px;

      @include notDesktop {
        flex-direction: column;
        padding: 0 30px;
      }

      .experience {
        display: flex;
        flex-direction: column;
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
  }
</style>

<div class="career">
  <h2 class="title g-wrapper">Experiencia</h2>

  <div class="experiences">
    {#each experiences as experience, i}
      <div class="experience" class:active={i === 3}>
        <span class="name" contenteditable={i === 3}>{experience.name}</span>
        <span class="date">{experience.date}</span>
        <span class="description" contenteditable={i === 3}>{experience.description}</span>
      </div>
    {/each}
  </div>

  <Opinions
    text="No aplico a trabajos para los que no estoy preparada."
    author="— Película que me vi la semana pasada"
    title="El exorcismo de Georgetown"
  />
</div>
