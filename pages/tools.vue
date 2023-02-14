<template>
  <v-container grid-list-xs>
    <v-tabs
      v-model="value"
      color="teal darken-1"
      dark
      slider-color="teal darken-1"
    >
      <v-tab>
        Төхөөрөмжийн жагсаалт <v-icon class="ml-2">mdi-list-box</v-icon></v-tab
      >
      <v-tab-item>
        <v-card flat
          ><v-card-title> Төхөөрөмжийн жагсаалт </v-card-title>
          <v-card-subtitle>2023.02.15</v-card-subtitle></v-card
        >
        <v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="10"
          class="elevation-1"
          color="teal darken-1"
        >
        </v-data-table>
      </v-tab-item>
      <v-tab> Төхөөрөмж нэмэх <v-icon class="ml-2">mdi-plus</v-icon></v-tab>
      <v-tab-item>
        <v-card
          ><v-card-title primary-title> Төхөөрөмж нэмэх </v-card-title>
          <v-form v-model="valid">
            <v-container>
              <v-row>
                <v-col cols="12" md="3">
                  <v-text-field
                    v-model="firstname"
                    color=" teal darken-1"
                    :rules="nameRules"
                    :counter="10"
                    label="Төхөөрөмжийн нэр"
                    required
                    hint="Төхөөрөмжийн нэрийг латинаар оруулна уу"
                  ></v-text-field>
                </v-col>

                <v-col cols="12" md="3">
                  <v-text-field
                    v-model="lastname"
                    color=" teal darken-1"
                    :rules="nameRules"
                    :counter="10"
                    label="Төхөөрөмжийн дугаар"
                    hint="Төхөөрөмжийн нэрийг латинаар оруулна уу"
                    required
                  ></v-text-field>
                </v-col>

                <v-col cols="12" md="3">
                  <v-text-field
                    v-model="email"
                    color=" teal darken-1"
                    :rules="emailRules"
                    label="Тоо ширхэг"
                    required
                    hint="Төхөөрөмжийн тоо ширхэгийг латинаар оруулна уу"
                  ></v-text-field> </v-col
                ><v-col cols="12" md="3">
                  <v-text-field
                    v-model="email"
                    color=" teal darken-1"
                    :rules="emailRules"
                    label="Үнэ (₮)"
                    required
                    hint="Төхөөрөмжийн үнийг оруулна уу"
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row
                ><v-col cols="12"
                  ><v-textarea
                    filled
                    auto-grow
                    color="teal darken-1"
                    label="Төхөөрөмжийн дэлгэрэнгүй"
                    rows="4"
                    row-height="30"
                  ></v-textarea
                ></v-col>
              </v-row>
            </v-container>
          </v-form>
          <v-card-actions class="d-flex justify-center align-center">
            <v-btn color="teal darken-1" @click="snackbar = true"
              >НТөхөөрөмжэх <v-icon class="ml-2">mdi-plus</v-icon></v-btn
            >
            <v-snackbar v-model="snackbar">
              {{ text }}

              <template v-slot:action="{ attrs }">
                <v-btn
                  color="error"
                  text
                  v-bind="attrs"
                  @click="snackbar = false"
                >
                  хаах
                </v-btn>
              </template>
            </v-snackbar>
          </v-card-actions>
        </v-card>
      </v-tab-item>
    </v-tabs>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      snackbar: false,
      text: "Амжилттай нТөхөөрөмжэгдлээ",
      valid: false,
      firstname: "",
      lastname: "",
      nameRules: [
        (v) => !!v || "Төхөөрөмжийн нэрийг оруулна уу",
        (v) => v.length <= 10 || "Name must be less than 10 characters",
      ],
      email: "",
      emailRules: [
        (v) => !!v || "Төхөөрөмжийн тоо ширхэгийг оруулна уу",
        (v) => /.+@.+/.test(v) || "E-mail must be valid",
      ],
      headers: [
        {
          text: "Төхөөрөмжийн нэр",
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
