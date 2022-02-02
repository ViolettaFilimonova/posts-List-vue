<template>
  <form @submit.prevent>
    <new-input
        v-model="post.title"
        type="text"
        placeholder="Название"
    />
    <new-input
        v-model="post.body"
        type="text"
        placeholder="Описание"
    />
    <new-button
        class="btn button"

        @click="createPost"
    >Создать
    </new-button>
  </form>
</template>

<script>
import NewButton from "@/components/UI/NewButton"
export default{
  components:{
    NewButton
  },
  data(){
    return{
      post:{
        title: '',
        body: '',
      }
    }
  },
  methods:{
    createPost(){
      this.post.id = Date.now()   ;
      this.$emit('create', this.post)
      this.post  = {
        title: '',
        body:'',
      }
    }
  }
}
</script>

<style scoped>
form{
  display: flex;
  flex-direction: column;
}
.button{
  align-self: flex-end;
  margin-top: 15px;
}


</style>