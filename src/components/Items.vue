<template>
  <div>
    <br />
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <template v-slot:activator="{ on }">
          <v-btn color="primary" v-on="on">Add Item</v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="headline">Add Item</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" sm="6" md="4">
                  <v-autocomplete
                    v-model="item.kind"
                    :items="['Van', 'Boat', 'Motorcycle', 'Car', 'Bus']"
                    label="Kind of Vehicles*"
                    required
                  ></v-autocomplete>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Brand*"
                    v-model="item.brand"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Sitting Capacity*"
                    v-model="item.sit"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Location*"
                    v-model="item.location"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Rate*"
                    v-model="item.rate"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
            <small>*indicates required field</small>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="blue darken-1"
              text
              v-on:click="$emit('cancel')"
              @click="dialog = true"
              >Close</v-btn
            >
            <v-btn
              color="blue darken-1"
              text
              v-on:click="$emit('AddItem', item)"
              @click="dialog = false"
              >Save</v-btn
            >
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </div>
</template>
<style scoped>
</style>
<script>
export default {
  name: "AddItem",
  data() {
    return {
      dialog: false,
      item: {
        kind: "",
        brand: "",
        sit: "",
        location: "",
        rate: ""
      }
    }
  }
  }
</script>
