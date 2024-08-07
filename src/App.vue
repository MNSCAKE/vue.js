<script setup>
import { ref } from 'vue'
const num = ref(0)
const htmltemplate = ' <h1>this is test</h1> '

setInterval(() => {
  num.value++
}, 500)

const text = ref('工作天')
const day = ref('8月6日')
const ischecked = ref('true')
const arraycheckbox = ref([])
const radiovalue = ref('male')

const imgurl = ref(
  'https://plus.unsplash.com/premium_photo-1722686516461-46770349c814?q=80&w=400&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
)
</script>

<template>
  <div>
    <h1>{{ text }}</h1>

    <input type="text" v-model="text" />
    {{ day }}
    <select name="" id="" v-model="day">
      <option value="8月6日">8月6日</option>
      <option value="8月7日">8月7日</option>
      <option value="8月8日">8月8日</option>
    </select>
    <hr />
    {{ ischecked }}
    <input type="checkbox" v-model="ischecked" />
    <input type="text" :disabled="ischecked" />
    <hr />
    {{ arraycheckbox }}
    <input type="checkbox" v-model="arraycheckbox" value="練功" />
    <input type="checkbox" v-model="arraycheckbox" value="練練功" />
    <input type="checkbox" v-model="arraycheckbox" value="練😍😍功" />

    <hr />
    {{ radiovalue }}
    <input type="radio" v-model="radiovalue" value="male" />
    <input type="radio" v-model="radiovalue" value="female" />

    <hr />

    <h1>讀秒{{ num }}</h1>

    {{ htmltemplate }}
    <div v-html="htmltemplate"></div>
    <!--  會出現h1未解決-->

    <hr />
    <img :src="imgurl" alt="" />
    <hr />
  </div>
</template>
