<template>
  <div class="heroImage">

  </div>
</template>
<script>
export default {
  name: 'HeroImage',
};
</script>
<style lang="scss" scoped>

  .heroImage{
    position: fixed;
    width: 100%;
    height: 100vh;
    top: 0;
    z-index: -1;
    background-image: url("../assets/background.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 40% 0;
  }

  .heroImage::before{
    content: '';
    background: #fff;
    position: absolute;
    opacity: 0.1;
    top: 0;
    left: 0;
    z-index: 1;
    width: 100%;
    height: 100vh;
  }

</style>
