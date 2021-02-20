<template>
  <ul class="list-group">
    <li class="list-group-item" v-for="(item,index) in deletes" :key="index">
      <div class="form-check">
        <label class="form-check-label" for="exampleCheck1">{{item}}</label>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
import { computed, defineComponent } from 'vue'
import store from '@/store'

export default defineComponent({
  setup () {
    return {
      deletes: computed(() => {
        return store.state.deletes
      })
    }
  }
})
</script>
