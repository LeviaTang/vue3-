<template>
  <div class="home">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand d-flex align-item-center" href="#">
        <div class="logo mr-2"></div>
        <span>TodoList</span>
      </a>
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <router-link class="nav-link" to="/add">代办事项</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/done">完成事项</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/delete">删除事项</router-link>
        </li>
      </ul>
    </nav>
    <div class="container">
      <router-view></router-view>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Home'
})
</script>

<style lang="scss" scoped>
  .logo {
    background: url('~@/assets/logo.png') no-repeat center center;
    background-size: contain;
    width: 40px;
    height: 40px;
  }
</style>
