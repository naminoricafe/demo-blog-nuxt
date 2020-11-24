<template>
  <v-card
    class="mx-auto"
    color="#F6F5EC"
  >
    <br>
    <v-toolbar
      color="#FFD180"
      class="contentsTitle"
    >
      <v-toolbar-title
        class="TOPICS">
      <h4>主なコンテンツ</h4></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-container
      class="main-contents">
      <v-row dense>
        <v-col cols="12">
          <v-hover v-slot:default="{ hover }">
          <nuxt-link to="/tebiki-top">
          <v-card
            color="#F6F5EC"
            :elevation="hover ? 12 : 2"
            :class="{ 'on-hover': hover }">
          <v-spacer></v-spacer>
            <v-card-title class="justify-center">
              <v-card-actions>
                <img src="~/static/kaisetsu-big.svg" width="300" height="200">
              </v-card-actions>
            </v-card-title>
          </v-card>
          </nuxt-link>
          </v-hover>
        </v-col>

        <v-col cols="12">
          <v-hover v-slot:default="{ hover }">
          <v-card
            color="#F6F5EC"
            :elevation="hover ? 12 : 2"
            :class="{ 'on-hover': hover }">

          <v-spacer></v-spacer>
            <v-card-title class="justify-center">
              <v-card-actions>
                <img src="~/static/ensyuu-big.svg" width="160" height="200">
              </v-card-actions>
            </v-card-title>
          </v-card>
          </v-hover>
        </v-col>

        <v-col cols="12">
          <v-hover v-slot:default="{ hover }">
          <v-card
            color="#F6F5EC"
            :elevation="hover ? 12 : 2"
            :class="{ 'on-hover': hover }">
          <v-spacer></v-spacer>
            <v-card-title class="justify-center">
              <v-card-actions>
                <img src="~/static/bunseki-big.svg" width="190" height="200">
              </v-card-actions>
            </v-card-title>
          </v-card>
          </v-hover>
        </v-col>

        <v-col cols="12">
          <v-hover v-slot:default="{ hover }">
          <v-card
            color="#F6F5EC"
            :elevation="hover ? 12 : 2"
            :class="{ 'on-hover': hover }">
          <v-spacer></v-spacer>
            <v-card-title class="justify-center">
              <v-card-actions>
                <img src="~/static/gaiyou-big.svg" width="200" height="200">
              </v-card-actions>
            </v-card-title>
          </v-card>
          </v-hover>
        </v-col>

        
      </v-row>
    </v-container>
  </v-card>
  </v-hover>
</template>

<style>

.v-card-subtitle{
  text-align:center;
}

.contents{
  background-color: #F6F5EC;
}

.v-card-title{
  text-align: center;
}
</style>