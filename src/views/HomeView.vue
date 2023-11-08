<script setup>
import { ref } from "vue"

const names = ref(["Snap", "fwths"])
const nameInput = ref("")


const addInvite = () => {
  names.value.unshift(nameInput.value);
  nameInput.value = "";
}

    const removeInvite = (invite) => {
      names.value.splice(names.value.indexOf(invite), 1);
    };
</script>

<template>
  <main>

   <div class="container">
      <input type="text" placeholder="Add person" v-model="nameInput" @keypress.enter="addInvite">
      <TransitionGroup name="invites">
          <li  v-for="name in names" :key="name" @click="removeInvite(name)">
            {{ name }}
          </li>
      </TransitionGroup>
   </div>
  </main>
</template>


<style scoped>
.container {
  font-family: 'Courier New', Courier, monospace;
  max-width: 300px;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}

.container input {
  width: 100%;
  border-radius: 5px;
  border: 1px solid rgba(128, 128, 128, 0.13);
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(131, 131, 131, 0.53);
}


.ha {
  display: flex;
  flex-direction: column;
  gap: 6px;
  list-style: none;
  margin: 0px;
  padding: 0px;
}

li{
  list-style: none;
  width: 300px;
  background-color: rgba(95, 95, 95, 0.53);
  border-radius: 5px;
  padding: 5px 10px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px rgba(192, 192, 192, 0.53);
  text-align: center;
  cursor: pointer;
}

.invites-enter-from {
  opacity: 0;
  transform: scale(0.5);
}

.invites-enter-to {
  opacity: 1;
  transform: scale(1);
}

.invites-enter-active {
  transition: all 1s ease;
}

.invites-leave-to {
  opacity: 0;
  transform: scale(0);
}

.invites-leave-active {
  transition: all 1s ease;
  position: absolute;
}

.invites-move {
  transition: all 0.5s ease;
}
</style>