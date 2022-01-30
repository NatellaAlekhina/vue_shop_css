<template>
  <div class="item">
    <div class="product card">
      <img :src="`./img/${data.img}`" />
      <div class="product-text-box">
        <p class="product-text">{{ data.title }}</p>
        <p class="product-price">{{ data.price }}$</p>
      </div>
    </div>

    <div class="box-add">
      <button class="add" v-on:click="onClick" v-if="target == 'showcase'">
        <img class="add-img" :src="`./img/cart-add.svg`" />
        Купить
      </button>
      <button v-on:click="onClick" v-if="target == 'cart'">Удалить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: ["data", "target"],
  methods: {
    onClick() {
      this.$emit("productAction", this.data);
    },
  },
};
</script>

<style lang="scss">
.card {
  //width: 30%;
  //border: 1px solid black;
  //padding: 10px;
  //display: flex;
  //flex-direction: column;
  //justify-content: space-between;
  //align-items: center;
  //margin-bottom: 20px;

  img {
    width: 100%;
  }
}
</style>