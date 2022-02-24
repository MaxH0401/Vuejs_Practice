<template>
  <div class="wrapper">
    <h2>Use Component</h2>

    <div style="padding-bottom: 20px">
      Hero Name : <input type="text" v-model="name" />
      <br />
      Price : <input type="number" v-model="price" />
      <br />
      <button @click="addHero">Add Hero</button>
    </div>

    <div class="product-list">
      <!-- <productItem name="Flash"></productItem> -->
      <!-- name沒有冒號的情況下是丟字串 -->
      <productItem
        v-for="product in products"
        :key="product.id"
        :name="product.name"
        :price="product.price"
      >
      </productItem>
      <!-- 有冒號(V-bind)的狀況下，就一定要丟變數 -->
    </div>

    <h2>No Component</h2>
    <div class="product-list">
      <div class="product-item" v-for="product in products" :key="product.id">
        <h3>{{ product.name }}</h3>
        {{ product.price }}
      </div>
    </div>
  </div>
</template>

<script>
import productItem from "@/components/ProductItem";
export default {
  name: "ProductsView",
  components: {
    productItem,
  },
  data() {
    return {
      name: "MAX",
      price: "",
      products: [
        {
          id: 1,
          name: "Spiderman",
          price: 100,
        },
        {
          id: 2,
          name: "HULK",
          price: 500,
        },
        {
          id: 3,
          name: "IronMan",
          price: 200,
        },
        {
          id: 4,
          name: "BatMan",
          price: 200,
        },
        {
          id: 5,
          name: "Wolverine",
          price: 500,
        },
        {
          id: 6,
          name: "Venom",
          price: 500,
        },
        {
          id: 7,
          name: "Starlord",
          price: 300,
        },
      ],
    };
  },
  methods: {
    addHero() {
      let name = this.name;
      let price = this.price;
      this.products.push({
        id: 5,
        name: name,
        price: price,
      });
    },
  },
};
</script>

<style>
.product-list {
  display: flex;
  flex-wrap: wrap;
}
.product-item {
  width: calc(25% - 10px);
  /* 25% 減 10px，是為了減margen造成的10px，如果沒減掉，那會被擠到下一行 */
  margin: 0 5px 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: 0 2px 5px #aaa;
  padding: 10px;
  background: #619b14;
  color: #f1f1f1;
}
</style>