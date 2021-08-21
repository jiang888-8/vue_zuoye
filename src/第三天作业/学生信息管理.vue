<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name"/>
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.number="age"/>
    </div>
    <div>
      <span>性别:</span>
      <select v-model="gender">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="add()">添加/修改</button>
    </div>
    <div>
      <table
        border="1"
        cellpadding="10"
        cellspacing="0"
      >
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item,index) in arr" :key="index">
          <td> {{item.id}} </td>
          <td>{{item.name}}</td>
          <td>{{item.age}}</td>
          <td>{{item.gender}}</td>
          <td>
            <button @click="del(index)">删除</button>
            <button @click="xg(index)">编辑</button>
          </td>
        </tr>
      </table>
      <p>年龄总和：{{ageSum}}</p>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      name:'',
      age:0,
      gender:'男',
      arr:[
        {
          id:1,
          name:'吴亦凡',
          age:28,
          gender:'男'
        }
      ],
      flig:false,
      ind:''
    }
  },

  computed: {
    ageSum () {
      return this.arr.reduce((sum,obj)=>{
        return sum += obj['age']
      },0)
    }
  },

  methods: {
    add () {
      if(!this.flig){
        if(!this.name || this.age === 0 || !this.age){
          return alert('请将个人信息填写完整！')
        }
        const id =this.arr.length === 0 ? 1 : this.arr[this.arr.length - 1].id +1
        this.arr.push({
          id:id,
          name:this.name,
          age:this.age,
          gender:this.gender
        })
        this.name = ''
        this.age = ''
      }else {
        if(!this.name || this.age === 0 || !this.age){
          return alert('请将个人信息填写完整！')
        }
        this.arr[this.ind].name = this.name
        this.arr[this.ind].age = this.age
        this.arr[this.ind].gender = this.gender
        this.name = ''
        this.age = ''
      }
    },

    del (index) {
      this.arr.splice(index,1)
    },

    xg (index) {
      console.log(this.arr[index]);
      this.flig = true
      this.name = this.arr[index].name
      this.age = this.arr[index].age
      this.gender = this.arr[index].gender
      this.ind = index
    }
    
    
  }
}
</script>

