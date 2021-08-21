<template>
  <div>
    <div style="display: inline-block" v-for="(item,index) in arr" :key="index">
      <input type="checkbox" v-model="newArr" :value="item">
      <span> {{item}} </span>
    </div>
    <p>你选中的元素, 累加的值和为: {{sum}}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      arr:[9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      newArr:[]
    }
  },

  computed: {
    sum () {
      //使用reduce，必须要在后面加循环一次的时间
      return this.newArr.reduce((num,value)=>{
        return num += value
      },0)
    }
  },

  methods: {

  }
}
</script>

<style scoped>

</style>

