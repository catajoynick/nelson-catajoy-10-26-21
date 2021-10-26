<template>
  <!-- App.vue -->

  <v-app>
    <!-- start: navigation drawer -->
    <v-navigation-drawer app v-model="drawer" clipped>
      <!-- start: navigation drawer image -->
      <v-card>
        <v-img
          height="300px"
          src="https://foundersguide.com/wp-content/uploads/2020/11/programming-1.jpg"
        >
        </v-img>
      </v-card>
      <!-- end: navigation drawer image -->

      <!-- start: dialog box -->
      <div class="text-center">
        <v-dialog v-model="dialog">
          <template v-slot:activator="{ on, attrs }">
            <v-btn color="primary" block v-bind="attrs" v-on="on">
              Read me
            </v-btn>
          </template>

          <v-card>
            <v-card-title>Hello there fren</v-card-title>
            <v-card-text>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit.
              Accusamus, alias!
            </v-card-text>
            <v-divider></v-divider>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="primary" text @click="dialog = false">
                I accept
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
      <!-- end: dialog box -->

      <!-- start: links -->

      <!-- start: data table link -->
      <v-list-item :to="{ name: 'data-table' }">
        <v-list-item-content>
          <v-list-item-title>
            <v-icon>mdi-file-table</v-icon> Data table</v-list-item-title
          >
        </v-list-item-content>
      </v-list-item>
      <!-- start: data table link -->

      <!-- start: data forms link -->
      <v-list-item :to="{ name: 'forms' }">
        <v-list-item-content>
          <v-list-item-title>
            <v-icon>mdi-form-select</v-icon> Forms</v-list-item-title
          >
        </v-list-item-content>
      </v-list-item>
      <!-- end: data forms link -->

      <!-- end: links -->
    </v-navigation-drawer>
    <!-- end: navigation drawer -->

    <!-- start: app bar  -->
    <v-app-bar app clipped-left>
      <!-- start: app nav icon -->
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <!-- end: app nav icon -->

      <v-spacer></v-spacer>

      <!-- start: drop down menu -->
      <div class="text-center mx-2">
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn color="primary" dark v-bind="attrs" v-on="on">
              Navigate
            </v-btn>
          </template>
          <v-list v-for="(item, index) in items" :key="index">
            <v-list-item :to="{ name: item.linkName }">
              <v-list-item-title>{{ item.linkText }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </div>
      <!-- end: drop down menu -->

      <!-- start: logout button -->
      <v-btn to="/"><v-icon>mdi-logout</v-icon>Sign out</v-btn>
      <!-- end: logout button -->
    </v-app-bar>

    <!-- end: app bar  -->

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      dialog: false,
      items: [
        { linkName: "data-table", linkText: "Data table" },
        { linkName: "forms", linkText: "Forms " }
      ]
    };
  }
};
</script>

<style></style>
