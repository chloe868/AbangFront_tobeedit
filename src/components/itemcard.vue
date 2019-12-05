<template>
  <div class="additem_card">
    <div class="kindofvehicle">
     Kind of Vehicle:  {{ kind }} <br />
     Brand:  {{ brand }}
    </div>
    <div class="sittingcapacity">Sitting Capacity : {{ sit }}</div>
    <div class="location">Location: {{ location }}</div>
    <div class="rate">Rate: {{ rate }}</div>
    <v-btn
      color="primary"
      class="md-accent delete_btn"
      v-on:click="$emit('deleteItemById', id)"
    >
      Delete
    </v-btn>
  </div>
</template>

<script>
export default {
  name: "AddItemCard",
  props: {
    id: String,
    kind: String,
    brand: String,
    sit: String,
    location: String,
    rate: String
  }
};
</script>

<style scoped>
</style>