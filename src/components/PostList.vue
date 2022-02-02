<template>
  <div v-if="posts.length > 0">
    <h3>Список постов</h3>
    <post-item
        v-for="post in posts"
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
    />
  </div>
  <h2 v-else class="empty-list">Список пуст</h2>
</template>

<script>
import PostItem from "./PostItem";
export default {
  components: {PostItem},
  props: {
    posts:{
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>
.empty-list{
  color: red;
}

</style>