<template>
  <div class="father">
    <h1>父组件子组件相互传值</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <h5>1:父组件向子组件传值</h5>
    <div><span>父组件：</span><input type="text" v-model="inputValue"></div>
    <child :fromFather="inputValue"></child>

     <!-- <h5>2:子组件向父组件传值</h5>
    <div><span>父组件：{{fromChild}}</span></div>
    <child v-on:fromChildValue="fromChildValueAction"></child> -->

  </div>
</template>

<script>
//引入子组件
import Child from '../components/Child.vue'
export default {
  name: 'Father',
  components:{
    'child':Child
  },
  data () {
    return {
      inputValue:'',
      fromChild:''
    }
  },
  methods:{
    // 子组件传过来的值
    fromChildValueAction(text){
      this.fromChild = text
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
