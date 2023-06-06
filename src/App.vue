<script setup>
import Tweet from "./components/Tweet.vue";
import axios from "axios";
</script>

<template>
  <div>
    <div class="header">
      <h1>Smartory Contacts!</h1>
    </div>

    <Tweet v-for="user in users" :key="user.id.value" :user="user" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios
        .get("https://randomuser.me/api/?results=20")
        .then((response) => {
          this.users = [response.data.results][0];
          console.log(this.users);
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
};
</script>

<style scoped>
img {
  max-width: 50px;
  max-height: 50px;
  border-radius: 50%;
}

.avatar {
  display: flex;
}
</style>
