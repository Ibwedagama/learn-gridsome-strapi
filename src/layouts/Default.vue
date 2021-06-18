<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title>Gridsome Events</v-toolbar-title>
      <v-text-field
        placeholder="Search an event"
        prepend-inner-icon="mdi-magnify"
        class="ml-8"
        outlined
        rounded
        dense
        hide-details
        style="max-width: 350px"
      />
      <v-spacer />
      <v-btn>Create an Event</v-btn>
    </v-app-bar>
    <v-main>
      <slot />
    </v-main>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName,
    siteDescription
  }
}
</static-query>
