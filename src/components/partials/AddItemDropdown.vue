<template>
  <div class="dropdown dropdown-hover dropdown-end">
    <div tabindex="0" class="m-1 btn btn-accent btn-circle btn-sm">
      <plus-icon class="h-5 w-5" />
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
import { PlusIcon } from '@heroicons/vue/solid'
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AddItemDropdown',
  components: {PlusIcon}
})
</script>
