<template>
  <div>
    <div class="box">
      <img :src="ImgUrl" >
      <p @click="del">{{Name}}</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  
  props: ['ImgUrl','Name','index'],


  created () {

  },

  methods: {
    del () {
      this.$emit('xiuGou',this.index)
    }
  }
}
</script>

<style scoped>
.box {
  float: left;
  width: 300px;
  border: 1px solid papayawhip;
  text-align: center;
}

.box img {
  width: 100%;
  height: 200px;
}
</style>
