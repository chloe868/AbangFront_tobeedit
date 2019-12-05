<template>
  <div>
  <Header />
    <v-container fluid>
      <v-row dense>
        <v-col v-for="card in cards" :key="card.title" :cols="flexall">
          <v-card>
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="400px"
            >
              <v-card-title v-text="card.title"></v-card-title>
            </v-img>

            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon color="blue">fab fa-facebook</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
import Header from "../components/Header.vue"
export default {
  components:{
    Header
  },
  data: () => ({
    drawer: false,
    flexall: 6,
    cards: [
      {
        title: "Catalina Car Tours",
        src:
          "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdOV2tPnIsNviEpIz9vSh-KQ83GsKVUJBabyB6xwQe-9OAZqMA&s",
        href: "https://www.facebook.com/CatalinaCarRentals07/about/"
      },
      {
        title: "Natalie Tours",
        src:
          "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT83qZMNcpMQjrDKTTm0EG9JureWn9qYmwoGn9pPwicqrD5yCIZ&s",
        href: "https://www.facebook.com/Natalie-Tours-351020815101736/"
      },
      {
        title: "Dream of Cebu",
        src:
          "https://apollo-singapore.akamaized.net/v1/files/zi70nd8jv8lp3-PH/image;s=1000x700;olx-st/_2_.jpg",
        href: "https://www.googleadservices.com/pagead/aclk?sa=L&ai=CGHJObJToXcVJidfaBK_wiIANlO7FtlKbkM-FyQqhrcSPpA0IABABIPO450Vg4cy5BaAB3JP7lAPIAQGpAhEa3SkWGFU-yAPYIKoEPU_Q0T26-buy0V1imOM5k4i4eaMLkerSnNZMuAeTTry5nHLuJN3pegCSEOiIdy47OFLBDqG_nUviesWFTG7ABNv6-OnlAYAFkE6gBlGAB4zshGuQBwGoB6a-G6gH2csbqAfPzBuoB_PRG6gH7tIbqAfC2hvYBwGwCAHSCAUQAiCEAZoJGGh0dHBzOi8vZHJlYW1vZmNlYnUuY29tL7EJ5PvHqXtnfR65CeT7x6l7Z30e-AkB&ved=2ahUKEwjEnO2V4p3mAhVM7WEKHeNvCFwQ0Qx6BAgcEAE&dblrd=1&val=GgjGOJwAZHtaeyABKAAwmf3Q7Puy-_jsATjCwZLrBUDUk6LvBQ&sig=AOD64_0yjWMosQnk0u6CWY0dPbNcHmN0-w&adurl=http://www.dreamofcebu.com/"
      },
      {
        title: "MotorCycleCity",
        src:
          "https://www.harley-davidson.com/content/dam/h-d/images/motorcycles/my19/softail/breakout/overview/dom/19-softail-breakout-hero.jpg",
        href: "https://www.facebook.com/MotorcycleCityMandaue/"
      }
    ]
  }),
  created() {
    window.addEventListener("resize", this.handleResize);
    this.handleResize();
  },
  destroyed() {
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    dashboard() {
      this.$router.push("/");
    },
    notify() {
      this.$router.push("/notifications");
    },
    item() {
      this.$router.push("/item");
    },
    profile() {
      this.$router.push("/profile");
    },
    handleResize() {
      if (window.innerWidth < 1200) {
        this.flexall = 12;
      } else {
        this.flexall = 6;
      }
    }
  }
};
</script>
