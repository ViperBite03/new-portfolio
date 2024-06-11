<script lang="ts">
  export let photo: string = 'https://letsenhance.io/static/8f5e523ee6b2479e26ecc91b9c25261e/1015f/MainAfter.jpg'
</script>

<style lang="scss">
  .container {
    position: absolute;
    border: 1px solid;
    filter: url(#round);

    right: 0;
    bottom: 100px;

    .blob {
      clip-path: polygon(60% 0, 100% 31%, 100% 83%, 42% 100%, 0% 70%, 5% 21%);
      height: 350px;
      width: 350px;

      img {
        object-fit: cover;
        width: 100%;
        height: 100%;
      }
    }
  }
</style>

<div class="container">
  <div class="blob"><img src={photo} alt="" /></div>

  <svg style="visibility: hidden; position: absolute;" width="0" height="0" xmlns="http://www.w3.org/2000/svg" version="1.1">
    <defs>
      <filter id="round">
        <feGaussianBlur in="SourceGraphic" stdDeviation="45" result="blur" />
        <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -9" result="goo" />
        <feComposite in="SourceGraphic" in2="goo" operator="atop" />
      </filter>
    </defs>
  </svg>
</div>
