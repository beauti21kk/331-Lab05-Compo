<template>
    <div class="no-underline	text-sky-800">
      <div class="p-5	w-64 cursor-pointer	border-2 border-solid	border-slate-500 mb-11">
        <h4>{{ event.title }}</h4>
        <h4>Category: {{ event.category }}</h4>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import type { EventItem } from '@/type'
  import type { PropType } from 'vue'
  const props = defineProps({
      event: {
          type: Object as PropType<EventItem>,
            require: true
      }
  })
  </script>
  
  <style scoped>
  .event-card {
    text-align: right;
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
  }
  
  .event-card:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
  }
  </style>
  