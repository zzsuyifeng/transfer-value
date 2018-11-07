<template>
  <div class="child">

    <!-- 父组件向子组件传值-子组件接收值 -->
    <div><span>子组件：{{fromFather}}</span></div>
    
    <!-- 子组件向父组件传值 -->
    <!-- <div><span>子组件：</span><button v-on:click="childValueAction">提交</button></div> -->

  </div>
</template>

<script>
export default {
  name: 'Child',
  props:{
    fromFather: String,//在父组件中接收值
    required: true
  },
  data () {
    return {
      childValue:'我是子组件中的值'
    }
  },
  methods:{
    childValueAction(){
      // 第一个参数fromChildValue是父组件v-on的监听方法
      this.$emit('fromChildValue',this.childValue)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
