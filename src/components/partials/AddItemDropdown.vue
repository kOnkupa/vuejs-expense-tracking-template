<template>
  <div class="dropdown dropdown-hover dropdown-end">
    <div tabindex="0" class="m-1 btn btn-accent btn-circle btn-sm">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M10 3a1 1 0 011 1v5h5a1 1 0 110 2h-5v5a1 1 0 11-2 0v-5H4a1 1 0 110-2h5V4a1 1 0 011-1z" clip-rule="evenodd" />
      </svg>
    </div>
    <ul tabindex="0" class="p-2 shadow-md menu dropdown-content bg-base-100 border-gray-300 border rounded-box w-52">
      <li>
        <a>Income</a>
      </li>
      <li>
        <a>Transaction</a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AddItemDropdown',
})
</script>
