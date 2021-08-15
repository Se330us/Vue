<template>
  <div class="app">
    <post-form
      @create="createPost">
    </post-form>
    <post-list 
    :posts="posts"
    ></post-list>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList"
export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        { id: 1, title: "Пост 1", body: "Описание поста 1" },
        { id: 2, title: "Пост 2", body: "Описание поста 2" },
        { id: 3, title: "Пост 3", body: "Описание поста 3" },
        { id: 4, title: "Пост 4", body: "Описание поста 4" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
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
