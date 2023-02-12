<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <!--  -->
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer">
        <v-icon :icon="mdiMenu" />
      </v-app-bar-nav-icon>

      <v-toolbar-title>Aurelien Rodot</v-toolbar-title>
    </v-app-bar>

    <v-main style="max-width: 500px;">
      <NuxtPage />
      <ContentList v-slot="{ list }" path="/blog">
        <div v-for="article in list" :key="article._path" style="min-height: 200px;">
          <h2>{{ article.title }}</h2>
          <ContentRenderer :value="article" excerpt />
        </div>
      </ContentList>
    </v-main>
  </v-app>
</template>


<script setup lang="ts">
import { mdiMenu } from "@mdi/js";
const drawer = ref(false);
</script>