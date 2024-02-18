<template>
  <v-app>
    <v-app-bar
      app
      color="indigo"
      dark
      elevation="4">
      <v-spacer/>
      <v-list-item-title class="text">
        ЭДО Максима
      </v-list-item-title>
      <v-btn right
        href="https://www.youtube.com/watch?v=dQw4w9WgXcQ&ab_channel=RickAstley"
        target="_blank"
        text>
        <v-icon>
          mdi-exit-to-app
        </v-icon>
      </v-btn>
      <div class="response">{{ response }}</div>
    </v-app-bar>
    <v-main>
      <div class="content">
          <NavigationBar/>
        <div class="right-content">
          <v-img
            src="./assets/image.jpg"
            max-width="700"
          />
          <div class="button">
            <v-btn color="red darken-1">
              <v-icon>mdi-thumb-up-outline</v-icon>Лайк</v-btn>
              <v-btn color="indigo darken-1">
              <v-icon>mdi-thumb-down-outline</v-icon>Дизлайк</v-btn>
              <v-btn color="light-blue">
              <v-icon>mdi-chevron-right</v-icon>Пропустить</v-btn>
          </div>
        </div>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import NavigationBar from './components/NavigationBar.vue';
import axios from 'axios';
export default {
  components: {
    NavigationBar,
  },
  data() {
    return {
      response: '' 
    };
  },
  mounted() {
    axios.get('https://numbersapi.com/42')
      .then(response => {
        this.response = response.data;
      })
    }
  };
</script>

<style>
.content {
  display: flex;
  justify-content: center;
  align-items: center;
  align-items: flex-start;
  height: 100%;
}

.right-content {
  padding-top: 30px;
  flex: 1;
  display: flex;
  flex-direction: column; 
  justify-content: flex-start; 
  align-items: center;
  margin-left: 20px;
}
.button{
  margin-top: 20px;
}
</style>
