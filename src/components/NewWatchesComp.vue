<template>
  <section class="release center">
    <p class="release__subheading">New watches</p>
    <h2 class="release__title">Green And Bronze—The Match Made In Heaven</h2>
    <div class="release-images">
      <img class="release_img" src="../assets/img/Rectangle9.png" alt="" />
      <img class="release_img" src="../assets/img/Rectangle8.png" alt="" />
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.release {
  padding-bottom: 80px;
  &__subheading {
    color: rgba(20, 20, 20, 0.4);
    font-size: 12px;
    font-weight: 300;
    line-height: 14px;
  }
  &__title {
    color: var(--darkGreen);
    font-size: 40px;
    font-weight: 600;
    line-height: 44px;
    margin-top: 8px;
    margin-bottom: 80px;
    max-width: 460px;
  }
  &-images {
    display: flex;
    justify-content: space-between;
  }
}
</style>
