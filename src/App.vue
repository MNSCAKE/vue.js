<script setup>
import { ref } from 'vue'
const num = ref(0)
const htmltemplate = ' <h1>餐點圖片</h1> '

setInterval(() => {
  num.value++
}, 500)

const text = ref('今日菜單')
const menu = ref('選單')
const imgurl = ref(
  'https://plus.unsplash.com/premium_photo-1722686516461-46770349c814?q=80&w=400&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
)
const ischecked = ref('true')
const arraycheckbox = ref([])
const radiovalue = ref('male')
const handleclick = () => {
  console.log('我被觸發了')
}
</script>

<template>
  <div>
    <h1>{{ text }}</h1>
    <input type="text" v-model="text" />

    {{ menu }}
    <select name="" id="" v-model="day">
      <option value="義大利麵">義大利麵</option>
      <option value="鮭魚佐黃檸">鮭魚佐黃檸</option>
      <option value="羊排特餐">羊排特餐</option>
    </select>

    <hr />
    <h1>請勿思考超過300,000秒喔{{ num }}</h1>

    {{ htmltemplate }}
    <div v-html="htmltemplate"></div>
    <!--  會出現h1未解決-->

    <hr />
    <img :src="imgurl" alt="" />
    <hr />

    <hr />
    {{ ischecked }}
    <input type="checkbox" v-model="ischecked" />
    <input type="text" :disabled="ischecked" />

    <div class="box" :style="{ transform: ischecked ? 'rotate(45deg)' : null }"></div>
    <div class="box" :style="{ backgroundColor: ischecked ? 'blue' : 'yellow' }"></div>
    <hr />
    {{ arraycheckbox }}
    <input type="checkbox" v-model="arraycheckbox" value="好吃" />
    <input type="checkbox" v-model="arraycheckbox" value="普普" />
    <input type="checkbox" v-model="arraycheckbox" value="美味😍😍" />

    <hr />
    {{ radiovalue }}
    <input type="radio" v-model="radiovalue" value="male" />
    <input type="radio" v-model="radiovalue" value="female" />

    <hr />

    <button type="button" @click="handleclick">主廚精選請點我</button>
    <h2>事件修飾符</h2>
    <a href="#" @click.prevent="handleclick">飲料請點我</a>
    <h2>按鍵修飾符</h2>
    <input type="text" v-on:keydown.enter="handleclick" />
  </div>
</template>
<style>
.box {
  height: 20px;
  width: 20px;
  background-color: brown;
  transition: 1s all;
}
</style>
