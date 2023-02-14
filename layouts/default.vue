<template>
  <v-app>
    <v-navigation-drawer app>
      <v-container class="d-flex justify-center align-center" grid-list-xs>
        <v-avatar size="72px">
          <v-img
            alt="Avatar"
            src="https://e0.pxfuel.com/wallpapers/43/832/desktop-wallpaper-doge-astro-samurai-doge-thumbnail.jpg"
          ></v-img>
        </v-avatar>
      </v-container>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Зуунбилэг </v-list-item-title>
          <v-list-item-subtitle> Dev team </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
          color="teal darken-1"
          link
          v-for="nav in navs"
          :key="nav"
          :to="nav.link"
        >
          <v-list-item-icon
            ><v-icon>{{ nav.icon }}</v-icon></v-list-item-icon
          >
          <v-list-item-content>
            <v-list-item-title class="text--secondary">{{
              nav.title
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-spacer></v-spacer>
      <v-card flat>
        <v-card-actions>
          <v-btn text plain block>Гарах</v-btn>
        </v-card-actions>
      </v-card>
    </v-navigation-drawer>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      navs: [
        {
          link: "/",
          icon: "mdi-home",
          title: "Нүүр",
        },
        {
          link: "/medicine",
          icon: "mdi-pill",
          title: "Эмийн бүртгэл",
        },
        {
          link: "/tools",
          icon: "mdi-toolbox",
          title: "Төхөөрөмжийн бүртгэл",
        },
        {
          link: "/edit",
          icon: "mdi-pen",
          title: "Бүртгэл нэмэх",
        },
        {
          link: "/profile",
          icon: "mdi-account",
          title: "Хэрэглэгч",
        },
      ],
    };
  },
};
</script>
<style></style>
