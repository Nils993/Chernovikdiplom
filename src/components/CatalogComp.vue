<template>
  <section class="catalog center">
    <h2 class="catalog__title">Catalog</h2>
    <div class="catalog-list">
      <div class="catalog-item" v-for="(watch, index) in watches" :key="index">
        <img :src="watch.src" alt="" />
        <h3 class="catalog-item__name">{{ watch.name }}</h3>
        <p class="catalog-item__price">{{ watch.price }}</p>
      </div>
    </div>
    <div class="catalog-wrap__btn">
      <button class="catalog__btn">Buy now</button>
    </div>
  </section>
</template>

<script>
import { mapState } from "vuex";

export default {
  data() {
    return {};
  },
  computed: {
    ...mapState(["watches"]),
  },
};
</script>

<style lang="scss" scoped>
.catalog {
  background: var(--white);
  padding-top: 160px;
  padding-bottom: 160px;
  &__title {
    color: var(--darkGreen);
    font-size: 40px;
    font-weight: 600;
    line-height: 44px;
  }
  &-list {
    display: grid;
    grid-template-columns: repeat(4, 276px);
    gap: 24px;
  }
  &-item {
    margin-top: 90px;
    &__name {
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      color: rgb(20, 20, 20);
      font-size: 14px;
      font-weight: 400;
      line-height: 20px;
      margin-top: 38px;
      margin-bottom: 4px;
    }
    &__price {
      color: rgba(20, 20, 20, 0.5);
      font-size: 12px;
      font-weight: 400;
      line-height: 14px;
    }
  }
  &-wrap__btn {
    display: flex;
    justify-content: flex-end;
  }
  &__btn {
    padding: 18px 35px;
    color: var(--white);
    font-size: 12px;
    font-weight: 400;
    line-height: 14px;
    text-align: center;
    text-transform: uppercase;
    background: var(--darkGreen);
    border-radius: 8px;
    align-self: flex-end;
    margin-top: 80px;
  }
}
</style>
