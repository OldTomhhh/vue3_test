<template>
name: <input type="text" v-model="data.name">
<br/>
age: <input type="text" v-model="data.age">
<br/>
comband: {{allName}}

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { reactive,computed,watch,ref } from 'vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup(){
    let data = ref({
      name:"jason",
      age:12
    })
    
    let allName = computed(()=>{
      return data.name + data.age
    })
    watch(data,(n,o)=>{
        console.log(n,o);
    })
    console.log(data)
    return{
      data,
      allName
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
