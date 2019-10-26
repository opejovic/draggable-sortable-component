<template>
  <div id="app" class="min-h-screen bg-gray-100 p-8">
    <div class=" bg-white mx-auto max-w-md rounded-lg shadow-lg py-8 px-4">
      
      <sortable-list v-model="todos" item-class="todo-item" handle-class="handle">
        <div slot-scope="{ items }">
          <sortable-item v-for="todo in items" :key="todo.id">
            <sortable-handle>
              <div class="bg-white px-4">
                  <div class="flex items-center border-b border-gray-200">
                    <div class="flex-grow flex items-center py-4">
                      <input type="checkbox" v-model="todo.complete" class="mr-3" />
                      <span>{{ todo.description }}</span>
                    </div>
                    <svg class="ml-2 h-4 w-4 cursor-move text-gray-500 hover:text-gray-900" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path fill-rule="evenodd" d="M14 4h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1zM8 4h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1zm6 6h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm-6 0h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm6 6h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1zm-6 0h2a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1v-2a1 1 0 0 1 1-1z" /></svg>
                  </div>
              </div>
            </sortable-handle>
          </sortable-item>
        </div>
      </sortable-list>
      
    </div>
  </div>
</template>

<script>
  import SortableList from "./components/SortableList"
  import SortableItem from "./components/SortableItem"
  import SortableHandle from "./components/SortableHandle"

  export default {
    name: "app",
    components: {
      SortableList,
      SortableItem,
      SortableHandle,
    },

    data() {
      return {
        todos: [
          { id: 1, description: "Do some learning boi", complete: false },
          { id: 2, description: "Learn More Vue", complete: false },
          { id: 3, description: "Learn MYSQL", complete: false },
          { id: 4, description: "Do some learning boi", complete: false },
        ]
      }
    },
  };
</script>

<style>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>
