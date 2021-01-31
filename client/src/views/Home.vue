<template>
  <div>
    <hr />
    <div class="list-unstyled" v-for="product in products" :key="product.id">
      <ul>
        <li class="media">
          <img
            v-if="product.images[0].src"
            class="mr-3"
            :src="product.images[0].src"
            :alt="product.images[0].alt"
          />
          <div class="media-body">
            <h4 class="mt-0 mb-1">{{ product.title }}</h4>
            <h5 class="mt-0 mb-1">{{ product.vendor }}</h5>
            {{ product.products }}
            <br />
            <small>{{ product.created_at }}</small>
          </div>
        </li>
      </ul>
      <hr />
    </div>
  </div>
</template>

<script>
/*eslint-disable */

const shopify_endpoint = 'toolio-retail.myshopify.com/admin/api/2019-10/products.json';
const API_URL = "http://localhost:3000/shopify?url=" + shopify_endpoint;

export default {
  name: "home",
  data: () => ({
    error: "",
    products: [],
    oatuh: "",
  }),

  mounted() {
    fetch(API_URL)
      .then((response) => response.json())
      .then((result) => {
        this.products = result;
      });
  },
  methods: {},
};

</script>

<style>
img {
  max-width: 300px;
  height: auto;
}
</style>
