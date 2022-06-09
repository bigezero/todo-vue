<template>
  <ul class="todo-list">
    <!-- completed: 完成的类名 -->
    <li class="completed" >
      <div class="view" v-for="(item,index) in listData" :key="index">
        <input class="toggle" type="checkbox" />
        <label>{{item}}</label>
        <button class="destroy"></button>
      </div>
    </li>
  </ul>
  
</template>

<script>
import eventBus from '../EventBus'
export default {
  data(){
    return{
      listData:['1','2','3']
    }
  },
  created(){
    eventBus.$on('send',(newContent)=>{
      this.listData.push(newContent)
    })
  }
}
</script>