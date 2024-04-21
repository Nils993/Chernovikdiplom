<template>
  <section id="catalog" class="catalog center">
    <h2 class="catalog__title">Catalog</h2>
    <div class="catalog-list">
      <div
        @click="toggleSelection(watch)"
        :class="{ selected: selectedWatch === watch }"
        class="catalog-item"
        v-for="watch in watches"
        :key="watch.id"
      >
        <img :src="watch.src" alt="" />
        <h3 class="catalog-item__name">{{ watch.name }}</h3>
        <p class="catalog-item__price">{{ watch.price }}</p>
      </div>
    </div>
    <div class="catalog-wrap__btn">
      <button class="catalog__btn" @click="openBuyForm">Buy now</button>
    </div>
    <BuyComp
      v-if="showBuyForm && selectedWatch"
      :selectedWatch="selectedWatch"
      @closeForm="closeBuyForm"
    />
  </section>
</template>

<script>
import { mapState } from "vuex";
import BuyComp from "@/components/BuyComp.vue";

export default {
  components: {
    BuyComp,
  },
  data() {
    return {
      selectedWatch: null,
      showBuyForm: false,
    };
  },
  computed: {
    ...mapState(["watches"]),
  },
  methods: {
    // selectWatch(watch) {
    //   this.selectedWatch = watch;
    //   console.log(watch.id);
    // },
    toggleSelection(watch) {
      if (this.isSelected(watch)) {
        this.selectedWatch = null;
        this.showBuyForm = false;
      } else {
        this.selectedWatch = watch;
      }
    },
    isSelected(watch) {
      return this.selectedWatch === watch;
    },
    openBuyForm() {
      if (!this.selectedWatch) {
        alert("Please select a watch first.");
        return;
      }
      this.showBuyForm = true;
    },
    closeBuyForm() {
      this.showBuyForm = false;
    },
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
    box-sizing: border-box;
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
    border: 1px solid var(--darkGreen);
    &:hover {
      border: 1px solid var(--white);
    }
  }
}
.selected {
  background: rgba(20, 20, 20, 0.1);
}
</style>
