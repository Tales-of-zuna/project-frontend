<template>
  <v-container grid-list-xs>
    <v-tabs v-model="value" color="teal darken-1" slider-color="teal darken-1">
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
      <v-tab> Төхөөрөмж <v-icon class="ml-2">mdi-toolbox</v-icon> </v-tab>
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
            ><v-col v-for="cardi in toolsdata" :key="cardi" cols="6" md="2">
              <v-card class="mx-auto" max-width="344">
                <v-img :src="cardi.img" height="200px"></v-img>

                <v-card-title> {{ cardi.name }} </v-card-title>

                <v-card-subtitle> 1,000 миллиграм </v-card-subtitle>
                <v-card-text>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                </v-card-text>
                <v-card-actions>
                  <v-btn
                    @click="cardi.quantity++"
                    icon
                    color="orange lighten-2"
                    text
                  >
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                  <v-text-field
                    name="name"
                    id="id"
                    v-model="cardi.quantity"
                    label="Тоо ширхэг"
                    color="teal"
                  ></v-text-field>
                  <v-btn
                    @click="cardi.quantity--"
                    icon
                    color="orange lighten-2"
                    text
                  >
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
      show: false,
      shirheg: 1,
      snackbar: false,
      text: "Амжилттай нэмэгдлээ",
      valid: false,
      firstname: "",
      lastname: "",
      toolsdata: [
        {
          quantity: 1,
          name: "Боолт",
          img: "https://www.narescue.com/media/catalog/product/cache/6c9c2a8706ce872329c582c5a62c8bc4/3/0/30-0027_b_2.jpg",
        },
        {
          quantity: 1,
          name: "Увч",
          img: "https://cdn.zochil.shop/e99cef8f-3d4b-45db-aa11-b50481ec6abd_t500.jpg",
        },
        {
          quantity: 1,
          name: "Солюкс",
          img: "https://a.allegroimg.com/s1024/0c6739/e777c57a450aa4e4d5d1e7a48e3a",
        },
        {
          quantity: 1,
          name: "Электрофорез",
          img: "https://palikha-clinic.ru/wp-content/uploads/2021/08/i-e1630322696713.jpg",
        },
        {
          quantity: 1,
          name: "Улаан гэрэл",
          img: "http://cdn.zochil.shop/01cf6267-6156-4cc0-ab65-8bfdd10c8a5c_t1500.jpg",
        },
        {
          quantity: 1,
          name: "Хануур",
          img: "https://www.jaseng.mn/wp-content/uploads/2015/12/aaaaaa.jpg",
        },
        {
          quantity: 1,
          name: "Бумба",
          img: "https://back.emonos.mn/media/product/image_1024.png",
        },
        {
          quantity: 1,
          name: "Утлага",
          img: "https://cdn.greensoft.mn/uploads/site/899/product/20200825181312_e0f00fdfc0917f5178862e875b018bc4.jpg",
        },
      ],
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
