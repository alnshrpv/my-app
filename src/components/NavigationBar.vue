<template>
  <v-navigation-drawer permanent>
    <v-list-item>
      <v-list-item-content>
        <v-list-item-title class="text-h6">
          Алина
        </v-list-item-title>
        <v-list-item-subtitle>
          Жестко кодит
        </v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
    <v-divider/>
    <v-list 
    dense 
    nav>
      <v-list-item 
      v-for="item in items" 
      :key="item.title" 
      link>
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "Входящие", icon: "mdi-arrow-bottom-left" },
        { title: "Исходящие", icon: "mdi-arrow-top-right" },
        { title: "История", icon: "mdi-history" }
      ],
    };
  }
};
</script>
