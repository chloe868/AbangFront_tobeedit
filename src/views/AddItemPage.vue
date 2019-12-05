<template>
  <div @click="showAddItem = true">
    <Header />
    <div class="result_part" >
      <div v-for="item in items" v-bind:key="item._id">
        <AddItemCard
          v-bind:id="item._id"
          v-bind:kind="item.kind"
          v-bind:brand="item.brand"
          v-bind:sit="item.sit"
          v-bind:location="item.location"
          v-bind:rate="item.rate"
          v-on:deleteItemById="deleteItemById"
        />
      </div>

      <AddItem v-if="showAddItem" v-on:cancel="showAddItem = false" />
    </div>
  </div>
</template>

<script>
// Import Components
import Header from "../components/Header.vue";
import AddItemCard from "../components/itemcard.vue";
import AddItem from "../components/Items.vue";
export default {
  name: "ArtistListPage",
  components: {
    Header,
    AddItemCard,
    AddItem
  },
  data() {
    return {
      items: [],
      showAddItem: false
    };
  },
  methods: {
    // Decomment the following function for do the question 2
    // addArtist(artist){
    //   // TODO question 2
    // }
    // Decomment the following function for do the question 3
    // deleteArtistById(artistId) {
    //   // TODO question 3
    // },
  }
};
</script>

<style lang="scss" scoped>
.result_part {
  grid-area: addItem_page;
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  justify-items: center;
  grid-column-gap: 10px;
  grid-row-gap: 15px;
}
.v-btn:not(.v-btn--outlined).primary, .v-btn:not(.v-btn--outlined).secondary, .v-btn:not(.v-btn--outlined).accent, .v-btn:not(.v-btn--outlined).success, .v-btn:not(.v-btn--outlined).error, .v-btn:not(.v-btn--outlined).warning, .v-btn:not(.v-btn--outlined).info {
    color: #FFFFFF;
    margin-left: 1550%;
    margin-top: -30%;
}
</style>
