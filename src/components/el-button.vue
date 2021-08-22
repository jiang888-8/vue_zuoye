<template>
  <div>
    <button :class="[type,size]">{{title}}</button>
  </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },

  props: ['type','title','size'],



  created () {

  },

  methods: {

  }
}
</script>

<style scoped>
button {
  width: 120px;
  height: 50px;
  background-color: #fff;
  border:1px solid #ccc
}
.primary {
  background-color: #409eff;
}
.success {
  background-color: #67c23a;
}
.info {
  background-color: #909399;
}
.warning {
  background-color: #e6a23c;
}
.danger {
  background-color: #f56c6c;
}

/*  */
.medium {
  width: 100px;
  height: 45px;
}
.small {
  width: 90px;
  height: 40px;
}
.mini {
  width: 70px;
  height: 30px;
}
</style>
