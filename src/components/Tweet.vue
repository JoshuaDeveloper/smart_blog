<template>
  <div class="tweet">
    <div class="avatar">
      <img :src="user.picture.thumbnail" alt="Avatar" />
    </div>
    <div class="content">
      <div>
        <author>{{ user.name.first }}</author>
        @{{ user.login.username }} {{ user.location.country }}
      </div>
      <div class="message">{{ user.location.street.name }}</div>
      <div>
        <iframe
          src="https://giphy.com/embed/1USKMDPjuH4ovL7J5h"
          width="480"
          height="370"
          frameBorder="0"
          class="giphy-embed"
          allowFullScreen
        ></iframe>
        <p>
          <a href="https://giphy.com/gifs/rick-and-morty-1USKMDPjuH4ovL7J5h"
            >via GIPHY</a
          >
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.tweet {
  min-width: 500px;
  display: flex;
  align-items: flex-start;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}
.message {
  color: white;
}

author {
  color: white;
  font-weight: bold;
}

img {
  max-width: 50px;
  max-height: 50px;
  border-radius: 50%;
}

.avatar {
  margin-right: 10px;
}

.content {
  display: flex;
  flex-direction: column;
}
</style>
