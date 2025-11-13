<template>
  <main class="text-5xl font-bold">Welcome to the trello app!</main>
  <div class="flex gap-5 py-5 overflow-x-auto">
    <div class="bg-gray-100 p-3 rounded-lg min-w-[250px] flex flex-col">
      <h2 class="font-medium mb-2">The list</h2>
      <div class="bg-white p-2 my-2 rounded shadow cursor-pointer">
        <span class="text-sm font-medium">Title Card</span>
        <p class="text-xs text-gray-400">Card Description</p>
      </div>

      <div class="bg-white p-2 my-2 rounded shadow cursor-pointer">
        <span class="text-sm font-medium">Title Card</span>
        <p class="text-xs text-gray-400">Card Description</p>
      </div>

      <button class="text-left text-sm text-gray-500 hover:text-gray-700">+ Add New Card</button>
    </div>
  </div>
</template>
