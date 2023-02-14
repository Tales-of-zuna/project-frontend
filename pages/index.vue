<template>
  <v-container grid-list-xs
    ><v-row
      ><v-col lg="3" md="6" cols="12"
        ><v-card>
          <v-card-title primary-title> Бүртгэл </v-card-title>
          <v-card-subtitle
            >Total
            <span class="text--primary font-weight-bold">48.5% Growth 😎</span>
            this month</v-card-subtitle
          ><v-card-actions class="d-flex justify-space-between">
            <div class="d-flex justify-center align-center">
              <v-btn color="success" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Эм </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn dark color="indigo" fab elevation="0" small
                ><v-icon>mdi-toolbox</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Төхөөрөмж </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn color="yellow" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> hello </v-card-text>
            </div>
          </v-card-actions>
        </v-card> </v-col
      ><v-col lg="3" md="6" cols="12"
        ><v-card>
          <v-card-title primary-title> Бүртгэл </v-card-title>
          <v-card-subtitle
            >Total
            <span class="text--primary font-weight-bold">48.5% Growth 😎</span>
            this month</v-card-subtitle
          ><v-card-actions class="d-flex justify-space-between">
            <div class="d-flex justify-center align-center">
              <v-btn color="success" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Эм </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn dark color="indigo" fab elevation="0" small
                ><v-icon>mdi-toolbox</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Төхөөрөмж </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn color="yellow" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> hello </v-card-text>
            </div>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col lg="3" md="6" cols="12"
        ><v-card>
          <v-card-title primary-title> Бүртгэл </v-card-title>
          <v-card-subtitle
            >Total
            <span class="text--primary font-weight-bold">48.5% Growth 😎</span>
            this month</v-card-subtitle
          ><v-card-actions class="d-flex justify-space-between">
            <div class="d-flex justify-center align-center">
              <v-btn color="success" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Эм </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn dark color="indigo" fab elevation="0" small
                ><v-icon>mdi-toolbox</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Төхөөрөмж </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn color="yellow" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> hello </v-card-text>
            </div>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col lg="3" md="6" cols="12"
        ><v-card>
          <v-card-title primary-title> Бүртгэл </v-card-title>
          <v-card-subtitle
            >Total
            <span class="text--primary font-weight-bold">48.5% Growth 😎</span>
            this month</v-card-subtitle
          ><v-card-actions class="d-flex justify-space-between">
            <div class="d-flex justify-center align-center">
              <v-btn color="success" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Эм </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn dark color="indigo" fab elevation="0" small
                ><v-icon>mdi-toolbox</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> Төхөөрөмж </v-card-text>
            </div>
            <div class="d-flex justify-center align-center">
              <v-btn color="yellow" fab elevation="0" small
                ><v-icon>mdi-pill</v-icon></v-btn
              >
              <v-card-text class="text--secondary"> hello </v-card-text>
            </div>
          </v-card-actions>
        </v-card>
      </v-col></v-row
    >
    <v-row
      ><v-col lg="6" cols="12"
        ><v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="5"
          class="elevation-1"
        >
        </v-data-table></v-col
      ><v-col lg="6" cols="12"
        ><v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="5"
          class="elevation-1"
        >
        </v-data-table></v-col></v-row
  ></v-container>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "Эмийн нэр",
          align: "start",
          sortable: false,
          value: "name",
        },
        { text: "Ширхэг (ш)", value: "calories" },
        { text: "Гарал ", value: "fat" },
        { text: "Ширхэг (ш)", value: "carbs" },
        { text: "Ширхэг (ш)", value: "protein" },
        { text: "Ширхэг (ш)", value: "iron" },
      ],
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: "Ulaanbaatar, Mongolia",
          carbs: 24,
          protein: 4.0,
          iron: 1,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: "Kyoto, Japan",
          carbs: 37,
          protein: 4.3,
          iron: 1,
        },
        {
          name: "Eclair",
          calories: 262,
          fat: "Xing Jiang, China",
          carbs: 23,
          protein: 6.0,
          iron: 7,
        },
        {
          name: "Cupcake",
          calories: 305,
          fat: "Seoul, Korea",
          carbs: 67,
          protein: 4.3,
          iron: 8,
        },
        {
          name: "Gingerbread",
          calories: 356,
          fat: "Jakarta, Indonasia",
          carbs: 49,
          protein: 3.9,
          iron: 16,
        },
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: "Ulaanbaatar, Mongolia",
          carbs: 24,
          protein: 4.0,
          iron: 1,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: "Kyoto, Japan",
          carbs: 37,
          protein: 4.3,
          iron: 1,
        },
        {
          name: "Eclair",
          calories: 262,
          fat: "Xing Jiang, China",
          carbs: 23,
          protein: 6.0,
          iron: 7,
        },
        {
          name: "Cupcake",
          calories: 305,
          fat: "Seoul, Korea",
          carbs: 67,
          protein: 4.3,
          iron: 8,
        },
        {
          name: "Gingerbread",
          calories: 356,
          fat: "Jakarta, Indonasia",
          carbs: 49,
          protein: 3.9,
          iron: 16,
        },
      ],
    };
  },
};
</script>

<style></style>
