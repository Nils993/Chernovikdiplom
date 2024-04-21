<template>
  <section id="about" class="about center">
    <h2 class="about__title">About us</h2>
    <div class="about-content">
      <div class="about-info">
        <p class="about__discription">
          Welcome to our premium watch collection, where luxury and style meet
          functionality and precision. Our selection of timepieces embodies the
          very best in Swiss craftsmanship and engineering, ensuring that you'll
          always have a reliable and stylish accessory on your wrist.
        </p>
        <p class="about__discription">
          At our premium watch collection, we believe that a watch is more than
          just a timekeeping device – it's a statement piece that reflects your
          personality and style. So why settle for anything less than the best?
          Browse our collection today and discover the perfect watch for you.
        </p>
      </div>

      <img class="about__banner" src="../assets/img/banerAboutUs.png" alt="" />
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.about {
  display: flex;
  justify-content: space-between;
  padding-top: 50px;
  padding-bottom: 50px;
  &-content {
  }
  &-info {
    display: flex;
    gap: 45px;
    margin-bottom: 40px;
  }
  &__title {
    color: var(--darkGreen);
    font-size: 40px;
    font-weight: 600;
    line-height: 44px;
  }
  &__discription {
    width: 400px;
    color: rgb(20, 20, 20);
    font-size: 14px;
    font-weight: 300;
    line-height: 18px;
  }
  &__banner {
    max-width: 892px;
    height: auto;
  }
}
</style>
