<template>
  <div class="buy center" v-if="selectedWatch">
    <div class="catalog-item">
      <img :src="selectedWatch.src" alt="" />
      <h3 class="catalog-item__name">{{ selectedWatch.name }}</h3>
      <p class="catalog-item__price">{{ selectedWatch.price }}</p>
    </div>
    <form class="form" action="#">
      <label class="form__label"
        >Full name
        <input
          class="form__input"
          type="text"
          placeholder="Enter your full name"
        />
      </label>
      <label class="form__label"
        >Email
        <input
          class="form__input"
          type="email"
          placeholder="Enter your email"
        />
      </label>
      <label class="form__label"
        >Card number
        <input class="form__input" type="text" placeholder="Enter card" />
      </label>

      <label class="form__label"
        >Comments
        <textarea
          class="form__input"
          cols="40"
          rows="10"
          placeholder="Enter your text"
        ></textarea>
      </label>
      <button class="form__but">submit</button>
      <p class="form__agree">
        By clicking on “Submit” button, you agree to our
        <a href="#">Privacy Policy</a> ,<br />
        and allow Promodo to use this information for marketing purposes.
      </p>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    selectedWatch: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      fullName: "",
      email: "",
      cardNumber: "",
      comments: "",
    };
  },
  methods: {
    submitForm() {
      // Handle form submission logic
      // For example, send form data to the server
      // Then emit event to close the form
      this.$emit("closeForm");
    },
  },
};
</script>

<style lang="scss" scoped>
.buy {
  padding-top: 40px;
  padding-bottom: 40px;
  display: flex;
  gap: 50px;
  justify-content: center;
}
.catalog {
  &-item {
    padding-top: 30px;
    width: 276px;
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
}
.form {
  display: flex;
  flex-direction: column;
  width: 508px;
  &__label {
    display: flex;
    flex-direction: column;
    color: var(--colorText);
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
  }
  &__input {
    appearance: none;
    padding: 12px 16px 12px 16px;
    border: 1px solid rgba(20, 20, 20, 0.5);
    border-radius: 8px;
    margin-top: 12px;
    margin-bottom: 24px;
    &::placeholder {
      color: var(--colorText);
      opacity: 0.5;
      font-size: 16px;
      font-weight: 400;
      line-height: 18px;
    }
  }
  &__but {
    padding: 18px;
    border-radius: 8px;
    background-color: var(--darkGreen);
    color: var(--white);
    font-size: 12px;
    font-weight: 400;
    line-height: 14px;
    text-align: center;
    text-transform: uppercase;
    margin-top: 16px;
    margin-bottom: 12px;
  }
  &__agree {
    color: rgba(20, 20, 20, 0.4);
    font-size: 12px;
    font-weight: 400;
    line-height: 14px;
    & a {
      color: rgba(20, 20, 20, 0.4);
      text-decoration: underline;
    }
  }
}
</style>
