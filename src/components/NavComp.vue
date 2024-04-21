<template>
  <ul class="nav">
    <li><a class="nav__item" href="#about">About us</a></li>
    <li><a class="nav__item" href="#catalog">Catalog</a></li>
    <li><a class="nav__item" href="#sale">Sale</a></li>
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
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    text-align: center;
    text-transform: uppercase;
  }
}
</style>
