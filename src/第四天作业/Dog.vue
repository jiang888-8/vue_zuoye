<template>
  <div class="box">
    <h1>选择你喜欢的修勾，买它</h1>
    <Dog v-for="(item,index) in arr" :key='index'
    :ImgUrl="item.dogImgUrl"
    :Name="item.dogName"
    :index='index'
    @xiuGou='fn'
    ></Dog>
  </div>
</template>

<script>
import Dog from './components/sell-dog.vue'
export default {
  data () {
    return {
      arr: [
        {
          dogImgUrl:
            "http://nwzimg.wezhan.cn/contents/sitefiles2029/10146688/images/21129958.jpg",
          dogName: "博美",
        },
        {
          dogImgUrl:
            "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1224576619,1307855467&fm=26&gp=0.jpg",
          dogName: "泰迪",
        },
        {
          dogImgUrl:
            "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2967740259,1518632757&fm=26&gp=0.jpg",
          dogName: "金毛",
        },
        {
          dogImgUrl:
            "https://pic1.zhimg.com/80/v2-7ba4342e6fedb9c5f3726eb0888867da_1440w.jpg?source=1940ef5c",
          dogName: "哈士奇",
        },
        {
          dogImgUrl:
            "https://img1.baidu.com/it/u=2466964629,2864648882&fm=26&fmt=auto&gp=0.jpg",
          dogName: "阿拉斯加",
        },
        {
          dogImgUrl:
            "https://img2.baidu.com/it/u=3418388867,1747097374&fm=26&fmt=auto&gp=0.jpg",
          dogName: "萨摩耶",
        },
      ],
    }
  },

  components: {
    Dog
  },

  methods: {
    fn (index) {
      this.arr.splice(index,1)
    }
  }
}
</script>

<style scoped>
.box {
  width: 920px;
  margin: auto;
}
</style>
