<script setup lang="ts">
import { ref } from 'vue'

  let count = ref(0)
  let styleButton = ref({
    color: 'red',
    fontSize: '20px'
  })
  let answer = ref(true)
  let messages = ref([
    { id: 1, text: 'Hello' },
    { id: 2, text: 'World' },
    { id: 3, text: '!' }
  ])
</script>

<template>
  <div class="about">
    <p v-if="answer">
      {{ count }}
    </p>
    <p v-else>
      {{ count + 5 }}
    </p>
    <button @click="answer = !answer" :style="styleButton">
      Add
    </button>
    <p v-for="(msg, i) in messages" :key="msg.id">
      {{ i }} - {{ msg.text }} ({{ msg.id }})
    </p>
  </div>
</template>

<style>

p {
  font-size: large;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.about {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>
