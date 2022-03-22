<template>
    <div class="card">
      <div class="card-content">
        <div class="content">
          <h4>{{ productItem.title }}</h4>
          <img v-bind:src="productItem.image_tag">
          <!-- <img src="../../assets/logo.png" alt=""> -->
          <a
            class="button is-rounded is-pulled-left"
            @click="addCartItem(productItem)"
          >
            <strong>Add to Cart</strong>
          </a>
          <br />
          <br />
          <p class="mt-4">
            {{ productItem.description }}
          </p>
        </div>
        <div class="media">
          <div class="media-content">
            <p class="title is-6">{{ productItem.owner }}</p>
            <p class="subtitle is-7">{{ productItem.email }}</p>
          </div>
          <div class="media-right">
            <a class="button is-primary is-light">
              <strong>$ {{ productItem.price }}</strong>
            </a>
          </div>
        </div>
      </div>
    </div>
</template>
<script>
import {mapActions} from 'vuex'
export default {
  name: "ProductListItem",
  props: ["productItem"],
  methods: {
    ...mapActions(["addCartItem"]),
  },
};
</script>
<style scoped>
 img {
  width: 100%;
  height: 200px;
  /* object-fit: cover; */
  object-fit: contain;
/*   object-fit: fill; */
}
</style>
