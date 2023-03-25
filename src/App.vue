<template>
  <div id="app">
    <div>
      <b-card
        :title="openedItem.title"
        :img-src="openedItem.image"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem"
        class="mb-2 m-5 p-5"
      >
        <b-card-text>
          {{ openedItem.desc }}
        </b-card-text>

        <b-button href="#" variant="primary">Go somewhere</b-button>
      </b-card>
    </div>
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <CardsComp :data="cards" @openItem="openTheItem"></CardsComp>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import CardsComp from "./components/CardsComp.vue";

export default {
  created() {
    fetch("https://dummyjson.com/products")
      .then((res) => res.json())
      .then((res) => (this.cards = res.products));
  },
  data() {
    return {
      cards: [],
      openedItem: [],
    };
  },
  components: {
    HelloWorld,
    CardsComp,
  },
  methods: {
    openTheItem(child) {
      this.openedItem.id = child.id;
      this.openedItem.title = child.title;
      this.openedItem.image = child.images[0];
      this.openedItem.desc = child.description;
      console.log(this.openedItem);
    },
  },
};
</script>
