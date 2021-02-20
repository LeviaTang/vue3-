<template>
  <div class="form-group">
    <label for="exampleInputEmail1">添加代办事项</label>
    <input type="text" class="form-control" v-model="inputValue" id="exampleInputEmail1" @keydown.enter="add(inputValue)">
    <small id="emailHelp" class="form-text text-muted">回车即可加入</small>
  </div>
  <ul class="list-group">
    <li class="list-group-item" v-for="(item,index) in todos" :key="index">
      <div class="form-check">
        <input type="checkbox" class="form-check-input" id="exampleCheck1" @click.prevent="check(index)">
        <label class="form-check-label" for="exampleCheck1">{{item}}</label>
        <div class="float-right">
          <button class="btn btn-danger" @click="delItem(index)">删除</button>
        </div>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">

import { computed, defineComponent, reactive, ref } from 'vue'
import store from '@/store'

export default defineComponent({
  setup () {
    const inputValue = ref('')

    const add = (value: string) => {
      if (value.trim() === '') return
      store.commit('add', value)
      inputValue.value = ''
    }

    const delItem = (index: number) => {
      store.commit('delete', index)
    }

    const check = (index: number) => {
      store.commit('check', index)
    }

    return reactive({
      inputValue,
      delItem,
      add,
      check,
      todos: computed(() => {
        return store.state.todos
      })
    })
  }
})
</script>
