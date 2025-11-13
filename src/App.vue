<script setup lang="ts">
import { reactive } from 'vue'
import Draggable from 'vuedraggable'
import Parent from './components/Parent.vue';

interface Card {
  id: number
  title: string
  description: string
}
interface List {
  id: number
  title: string
  cards: Card[]
}

const lists = reactive<List[]>([
  {
    id: 1,
    title: 'The list',
    cards: [
      { id: 1, title: 'Title Card', description: 'Card Description' },
      { id: 2, title: 'Title Card', description: 'Card Description' },
      { id: 3, title: 'Title Card', description: 'Card Description' },
    ],
  },
  {
    id: 2,
    title: 'In progress',
    cards: [
      { id: 1, title: 'Title Card', description: 'Card Description' },
      { id: 2, title: 'Title Card', description: 'Card Description' },
      { id: 3, title: 'Title Card', description: 'Card Description' },
    ],
  },
  {
    id: 3,
    title: 'Done',
    cards: [
      { id: 1, title: 'Title Card', description: 'Card Description' },
      { id: 2, title: 'Title Card', description: 'Card Description' },
      { id: 3, title: 'Title Card', description: 'Card Description' },
    ],
  },
])
</script>

<template>
  <main class="p-5 font-sans">Welcome to the trello app!</main>

  <div class="flex gap-5 py-5 overflow-x-auto">
    <div
      class="bg-gray-100 p-3 rounded-lg min-w-[250px] flex flex-col"
      v-for="list in lists"
      :key="list.id"
    >
      <h2 class="font-medium mb-2">{{ list.title }}</h2>

      <Draggable :list="list.cards" group="cards">
        <template #item="{ element }">
          <div class="bg-white p-2 my-2 rounded shadow cursor-pointer">
            <span class="text-sm font-medium">{{ element.title }}</span>
            <p class="text-xs text-gray-400">{{ element.description }}</p>
          </div>
        </template>
      </Draggable>

      <button class="text-left text-sm text-gray-500 hover:text-gray-700">+ Add New Card</button>
    </div>
    <Parent>
      
    </Parent>
  </div>
</template>
