<template>
  <ul class="nav">
    <li><a class="nav__item" href="">About us</a></li>
    <li><a class="nav__item" href="">Catalog</a></li>
    <li><a class="nav__item" href="">sale</a></li>
  </ul>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.nav {
  display: flex;
  gap: 40px;
  list-style-type: none;
  &__item {
    color: var(--white);
    font-size: 10px;
    font-weight: 400;
    line-height: 12px;
    letter-spacing: 0%;
    text-align: center;
    text-transform: uppercase;
  }
}
</style>
