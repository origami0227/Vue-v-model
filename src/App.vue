<template>
  <div id="app">
    三选一：{{ x }}
    <label>
      <span>抽烟:</span>
      <input type="radio" name="want " v-model="x" :value="1" />
    </label>
    <label>
      <span>喝酒:</span>
      <input type="radio" name="want" v-model="x" :value="2" />
    </label>
    <label>
      <span>烫头:</span>
      <input type="radio" name="want" v-model="x" :value="3" />
    </label>
    <hr>
    爱好：{{ y }}
    <label>
      <span>抽烟:</span>
      <input type="checkbox" name="want " v-model="y" :value="1" />
    </label>
    <label>
      <span>喝酒:</span>
      <input type="checkbox" name="want" v-model="y" :value="2" />
    </label>
    <label>
      <span>烫头:</span>
      <input type="checkbox" name="want" v-model="y" :value="3" />
    </label>
    <hr>
    爱好（下拉列表）:{{ z }}
    <br>
    <select v-model="z">
      <option value="">请选择</option>
      <option v-for="item in array" :value="item.value" :key="item.value">{{ item.text }}</option>
    </select>
    <hr>
    登陆
    <form @submit.prevent="onSubmit">
      <label>
        <span>用户名</span>
        <input type="text" v-model="user.username" />
      </label>
      <label>
        <span>密码</span>
        <input type="password" v-model="user.password" />
      </label>
      <button type="submit">登陆</button>
    </form>


  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      user: {
        username: '',
        password: ''
      },
      x: '',
      y: [],
      z: '',
      array: [
        { text: '抽烟', value: 1 },
        { text: '喝酒', value: 2 },
        { text: '烫头', value: 3 }
      ]
    }
  },
  methods: {
    onSubmit() {
      console.log(this.user)
    }
  }
}
</script>


