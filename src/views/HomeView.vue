<script setup>
import { ref } from "vue"

const showText = ref(true)
</script>

<template>
  <main>
    <div class="container">
      <Transition name="fade">
        <h1 id="hey" v-if="showText">Hey</h1>
        <h1 id="bye" v-else>GoodBye</h1>
      </Transition>
    </div>
   <button @click="showText = !showText">Toggle</button>
  </main>
</template>


<style scoped>

.fade-enter-from {
 opacity: 0;
}

.fade-enter-active {
  transition: all 5s ease;
}

.fade-leave-to {
  opacity: 0;
}

.fade-leave-active {
  transition: all 3.5s ease-out;
}

.container {
  position: relative;

}

h1{
  position: absolute;
}
button{
  margin-top: 50px;
}
</style>