<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useMessageStore } from '@/stores/message'
import { storeToRefs } from 'pinia'
const store = useMessageStore()
const { message } = storeToRefs(store)
import { ref } from 'vue'
const sizes = ref<number>(2)
</script>

<template>
  <div>
    <img
      alt="Vue logo"
      class="mt-5 m-auto mb-10 object-center h-28 w-72"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />
  </div>
  <header class="max-h-screen leading-normal">
    <!-- <div class="wrapper"> -->
    <!-- <HelloWorld msg="You did it!" /> -->

    <nav class="sm:flex justify-center items-center">
      <div class="space-x-5">
        <RouterLink class="hover:bg-lime-400 hover:text-white" :to="{ name: 'EventList' }">Home</RouterLink>
        <RouterLink class="hover:bg-lime-400 hover:text-white" :to="{ name: 'about' }">About</RouterLink>
        <RouterLink class="hover:bg-lime-400 hover:text-white" :to="{ name: 'category' }">Category</RouterLink>
        <RouterLink class="hover:bg-lime-400 hover:text-white" :to="{ name: 'student' }">Student</RouterLink>
      </div>
      <div id="flashMessage" v-if="message">
        <h4>{{ message }}</h4>
      </div>
    </nav>
    <!-- <h1>Events For Good</h1> -->
    <!-- </div> -->
  </header>
  <RouterView />
</template>

<style scoped>
/* .logo {
  display: block;
  margin: 0 auto 2rem;
} */

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
h4 {
  font-size: 20px;
}
@keyframes yellowfade {
  from {
    background: yellow;
  }
  to {
    background: transparent;
  }
}

#flashMessage {
  animation: yellowfade 3s ease-in-out;
}
</style>
