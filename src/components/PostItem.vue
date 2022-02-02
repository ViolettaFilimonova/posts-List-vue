<template>
  <div class="post" >
    <div>
      <div><strong>Название:</strong>{{post.title}}</div>
      <div><strong>Описание:</strong>{{post.body}}</div>
    </div>
    <div class="post__btn">
      <new-button
      @click="$emit('remove', post)"
      >Удалить </new-button>
    </div>
  </div>

</template>

<script>

  export default {

    props: {
      post: {
        type: Object,
        required: true,
      }
    }
  }
</script>

<style scoped>
.post{
  width: 100%;
  padding: 15px;
  margin-top: 15px;
  border: 2px solid teal;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>