<template>
  <Layout>
    <v-container>
      <v-row>
        <v-col sm="6" sm-offset="3">
          <!-- <v-tabs v-model="tab" grow>
            <v-tab>Item One</v-tab>
            <v-tab>Item Two</v-tab>
            <v-tab>Item Three</v-tab>
          </v-tabs> -->

          <v-card class="mx-auto mb-4" max-width="300" v-for="edge in $page.events.edges" :key="edge.node.id">
            <v-card-title>{{edge.node.title}}</v-card-title>
            <v-card-subtitle>{{edge.node.date}}</v-card-subtitle>
            <v-card-text class="text--primary">
              {{edge.node.description}}
            </v-card-text>
            <v-card-actions>
              <v-btn color="orange" text>
                See Details
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<page-query>
query {
  events: allEvent {
    edges {
      node {
        id
        title
        description
        date
        duration
        price
      }
    }
    totalCount
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!',
  },
  data() {
    return {
      tab: 0,
    }
  },
  watch: {
    tab(val){
      if (this.tab === 0){
        this.showAllEvents()
      } else {
        this.showEventsByType()
      }
    }
  },
  methods: {
    showAllEvents(){
      console.log('all')
    },
    showEventsByType(){
      console.log('type`')
    }
  }

}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
