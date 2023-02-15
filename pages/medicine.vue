<template>
  <v-container grid-list-xs>
    <v-tabs v-model="value" color="teal darken-1" slider-color="teal darken-1">
      <v-tab> Эмийн жагсаалт <v-icon class="ml-2">mdi-list-box</v-icon></v-tab>
      <v-tab-item>
        <v-card flat
          ><v-card-title primary-title> Эмийн жагсаалт </v-card-title>
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
      <v-tab> Эм нэмэх <v-icon class="ml-2">mdi-plus</v-icon></v-tab>
      <v-tab-item>
        <v-card
          ><v-card-title primary-title> Эм нэмэх </v-card-title>
          <v-form v-model="valid">
            <v-container>
              <v-row>
                <v-col cols="12" md="3">
                  <v-text-field
                    v-model="firstname"
                    color=" teal darken-1"
                    :rules="nameRules"
                    :counter="10"
                    label="Эмийн нэр"
                    required
                    hint="Эмийн нэрийг латинаар оруулна уу"
                  ></v-text-field>
                </v-col>

                <v-col cols="12" md="3">
                  <v-text-field
                    v-model="lastname"
                    color=" teal darken-1"
                    :rules="nameRules"
                    :counter="10"
                    label="Эмийн дугаар"
                    hint="Эмийн нэрийг латинаар оруулна уу"
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
                    hint="Эмийн тоо ширхэгийг латинаар оруулна уу"
                  ></v-text-field> </v-col
                ><v-col cols="12" md="3">
                  <v-text-field
                    v-model="email"
                    color=" teal darken-1"
                    :rules="emailRules"
                    label="Үнэ (₮)"
                    required
                    hint="Эмийн үнийг оруулна уу"
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row
                ><v-col cols="12"
                  ><v-textarea
                    filled
                    auto-grow
                    color="teal darken-1"
                    label="Эмийн дэлгэрэнгүй"
                    rows="4"
                    row-height="30"
                  ></v-textarea
                ></v-col>
              </v-row>
            </v-container>
          </v-form>
          <v-card-actions class="d-flex justify-center align-center">
            <v-btn color="teal darken-1" @click="snackbar = true"
              >Нэмэх <v-icon class="ml-2">mdi-plus</v-icon></v-btn
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
      <v-tab> Эм <v-icon class="ml-2">mdi-pill</v-icon> </v-tab>
      <v-tab-item>
        <v-container grid-list-xs>
          <v-col cols="6"
            ><v-text-field
              color="teal darken-1"
              name="name"
              append-icon="mdi-magnify"
              label="Хайх"
              id="id"
            ></v-text-field
          ></v-col>

          <v-row
            ><v-col v-for="cardi in 12" :key="cardi" cols="6" md="2">
              <v-card class="mx-auto" max-width="344">
                <v-img
                  src="https://cdn.theatlantic.com/thumbor/tNoE87U1vaH-U0osP0q3J0on9fo=/400x0:1429x1029/540x540/media/img/mt/2021/10/molnu_capsule3/original.jpg"
                  height="200px"
                ></v-img>

                <v-card-title> Aspirin </v-card-title>

                <v-card-subtitle> 1,000 миллиграм </v-card-subtitle>
                <v-card-text>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                </v-card-text>
                <v-card-actions>
                  <v-btn @click="shirheg++" icon color="success" text>
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                  <v-text-field
                    name="name"
                    id="id"
                    v-model="shirheg"
                    color="teal"
                  ></v-text-field>
                  <v-btn @click="shirheg--" icon color="error " text>
                    <v-icon>mdi-minus</v-icon>
                  </v-btn>
                  <v-spacer></v-spacer>

                  <v-btn icon @click="show = !show">
                    <v-icon>{{
                      show ? "mdi-chevron-up" : "mdi-chevron-down"
                    }}</v-icon>
                  </v-btn>
                </v-card-actions>

                <v-expand-transition>
                  <div v-show="show">
                    <v-divider></v-divider>

                    <v-card-text>
                      I'm a thing. But, like most politicians, he promised more
                      than he could deliver. You won't have time for sleeping,
                      soldier, not with all the bed making you'll be doing. Then
                      we'll go with that data file! Hey, you add a one and two
                      zeros to that or we walk! You're going to do his laundry?
                      I've got to find a way to escape.
                    </v-card-text>
                  </div>
                </v-expand-transition>
              </v-card></v-col
            ></v-row
          >
        </v-container>
      </v-tab-item>
    </v-tabs>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      shirheg: 1,
      show: false,
      snackbar: false,
      text: "Амжилттай нэмэгдлээ",
      valid: false,
      firstname: "",
      lastname: "",
      nameRules: [
        (v) => !!v || "Эмийн нэрийг оруулна уу",
        (v) => v.length <= 10 || "Name must be less than 10 characters",
      ],
      email: "",
      emailRules: [
        (v) => !!v || "Эмийн тоо ширхэгийг оруулна уу",
        (v) => /.+@.+/.test(v) || "E-mail must be valid",
      ],
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
