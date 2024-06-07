<script lang="ts">
  interface IContact {
    name: string
    content: string
    url: string
    svg: string
  }

  const links: IContact[] = [
    {
      name: '',
      content: 'LinkedIn',
      url: 'https://www.linkedin.com/in/laia-martin-de-la-fuente-660031280/',
      svg: '',
    },
    {
      name: '',
      content: 'GitHub',
      url: 'https://github.com/ViperBite03',
      svg: '',
    },
    {
      name: 'Email',
      content: 'lamadelafu03@gmail.com',
      url: '',
      svg: '',
    },
    {
      name: 'Teléfono',
      content: '671 707 263',
      url: '',
      svg: '',
    },
    {
      name: '(por si no lo habias hecho ya)',
      content: 'Descarga mi currículum',
      url: '',
      svg: '',
    },
  ]
</script>

<style lang="scss">
  .contact {
    height: 100vh;
    display: flex;
    flex-direction: column;

    .links {
      display: flex;
      flex-direction: column;
    }
  }
</style>

<div class="contact g-wrapper">
  <h2 class="title">¿Alguna duda? Hablemos</h2>

  <div class="links">
    {#each links as link}
      <a href={link.url} class="link">{link.content}</a>
    {/each}
  </div>
</div>
