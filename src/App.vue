<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
        v-bind:value="title"
        @input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Название"
      />
      <input
        v-bind:value="body"
        @input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Описание"
      />
      <button 
      class="btn" 
      @click="createPost">
      Создать
      </button>
    </form>
  </div>
  <div class="post" v-for="post in posts">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Название:</strong> {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "Пост 1", body: "Описание поста 1" },
        { id: 2, title: "Пост 2", body: "Описание поста 2" },
        { id: 3, title: "Пост 3", body: "Описание поста 3" },
        { id: 4, title: "Пост 4", body: "Описание поста 4" },
      ],
      title: "",
      body: "",
    };
  },
  methods: {
    createPost(event) {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = "";
      this.body = "";
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
.post {
  padding: 15px;
  border: 1px solid black;
  margin-top: 15px;
}
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid black;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: black;
  border: 1px solid black;
}
</style>
