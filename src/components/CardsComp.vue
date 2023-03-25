<template>
  <div class="container">
    <div class="row">
      <table class="table table-striped table-hover">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Title</th>
            <th scope="col">Description</th>
            <th scope="col">Images</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in data" :key="item.id">
            <th scope="row">{{ item.id }}</th>
            <td>{{ item.title }}</td>
            <td>{{ item.description }}</td>
            <td>
              <img width="50px" height="50px" :src="item.images[0]" alt="Hi" />
            </td>
            <td>
              <b-button variant="success m-3" @click="openItem(item)"
                >Open</b-button
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardsComp",
  props: ["data", "displayedItem"],
  methods: {
    openItem(item) {
      this.$emit("openItem", item);
    },
  },
};
</script>
