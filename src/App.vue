<template>
<div class="app">
  <post-form @create="createPost"/>
  <post-list
      :posts="posts"
      @remove="removePost"
  />
</div>

</template>

<script>
import PostForm from "./components/PostForm"
import PostList from "./components/PostList"
export default {
  components: {
    PostForm, PostList
  },
  data(){
    return{
      posts:[
        {id: 1, title: 'JavaScript', body: 'Описание поста'},
        {id: 2, title: 'JS', body: 'Описание '},
        {id: 3, title: 'Java', body: 'Пост'},
      ],
    }
  },
  methods: {
   createPost(post){
      this.posts.push(post)
   },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app{
  padding: 20px;
}


</style>