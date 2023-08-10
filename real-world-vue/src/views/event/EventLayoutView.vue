<script setup lang="ts">
import { useRouter } from 'vue-router';
import { useEventStore } from '@/stores/event'
import { storeToRefs } from 'pinia'
import { ref } from 'vue'

const router = useRouter()
const store = useEventStore()
const event = storeToRefs(store).event
const id = ref(event?.value?.id)

</script>

<template>
    <div v-if="event" class="text-center">
    <h1 class="font-bold">{{ event.title }}</h1>
    <div id="nav">
        <router-link class="hover:text-lime-400" :to="{ name: 'event-detail', params:{ id } }">Details</router-link>
        |
        <router-link class="hover:text-lime-400" :to="{ name: 'event-register', params: { id } }">Register</router-link>
        |
        <router-link class="hover:text-lime-400" :to="{ name: 'event-edit', params: { id } }">Edit</router-link>
    </div>

    <RouterView :event="event"></RouterView>
</div>
</template>