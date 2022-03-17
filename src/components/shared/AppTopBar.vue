<template>
  <div class="app-top-bar-events">
    <v-app id="inspire">
      <v-app-bar app absolute color="#43a047" dark prominent src="soccer.jpg">
        <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(55,236,186,.7), rgba(25,32,72,.7)"
          ></v-img>
        </template>

        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

        <v-app-bar-title>Primeiro-projeto</v-app-bar-title>

        <v-spacer></v-spacer>

        <v-col cols="auto" sm="6" md="3">
          <v-text-field
            placeholder="Search"
            prepend-inner-icon="mdi-magnify"
            class="expanding-search md-1 closed"
            filled
            dense
          ></v-text-field>
        </v-col>
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" app>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="text-h6"> Vuetify </v-list-item-title>
            <v-list-item-subtitle> for Iteris </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list dense nav>
          <v-list-item
            v-for="item in items"
            :key="item.title"
            link
            :to="item.to"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main>
        <router-view></router-view>
      </v-main>
    </v-app>
  </div>
</template>


<script>
export default {
  name: "AppTopBar",
  data: () => ({
    drawer: null,
    items: [
      { title: "That's it", icon: "mdi-format-list-checks", to: "/" },
      { title: "About", icon: "mdi-help-box", to: "/about" },
    ],
    right: null,
  }),
};
</script>
    
    <style scoped>
.app-top-bar a {
  text-decoration: none;
}

</style>
