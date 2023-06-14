<script setup>
import { ref } from 'vue'

const name = ref('')
</script>

<template>
  <nav class="navbar bg-primary">
    <div class="container-fluid ">
      <img src="../assets/undefined-Imgur.png" class="navbar-brand" alt="">
      <div class="d-flex">
        <input class="form-control me-2" type="search" placeholder="Ingresa tu usuario" aria-label="Search"
          id="name-field" v-model="name" @change="addName(name)">
      </div>
    </div>
  </nav>
</template>
<script>

export default {
  name: 'NavBar',

  methods: {
    addName: function (text) {
      this.$emit('addName', text)
    }
  },
  data: function () {
    return {

    }
  }
}
</script>

