<template>
  <TransitionRoot as="template" :show="open">
    <Dialog as="div" class="fixed inset-0 overflow-hidden z-50" @close="onClick">
      <div class="absolute inset-0 overflow-hidden">
        <DialogOverlay class="absolute inset-0" />
        <div class="fixed inset-y-0 left-0 pr-10 max-w-full flex">
          <TransitionChild
            as="template"
            enter="transform transition ease-in-out duration-500 sm:duration-700"
            enter-from="-translate-x-full"
            enter-to="translate-x-0"
            leave="transform transition ease-in-out duration-500 sm:duration-700"
            leave-from="translate-x-0"
            leave-to="-translate-x-full"
          >
            <div class="w-screen max-w-md">
              <div class="h-full flex flex-col py-6 bg-primary shadow-xl overflow-y-scroll">
                <div class="px-4 sm:px-6">
                  <div class="flex items-start justify-between">
                    <div class="mr-3 h-7 flex items-center">
                      <button
                        type="button"
                        class="rounded-md text-white hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                        @click="onClick"
                      >
                        <span class="sr-only">Close panel</span>
                        <chevron-double-left-icon class="h-6 w-6" aria-hidden="true" />
                      </button>
                    </div>
                    <DialogTitle class="text-lg font-medium text-white">Fancy Logo</DialogTitle>
                  </div>
                </div>
                <div class="mt-6 relative flex-1">
                  <!-- Replace with your content -->
                  <div class="relative text-white space-y-3 px-2 h-full">
                    <the-sidebar-link v-for="(navigation, key) in navigations" :key="key" :label="navigation.title" :icon="navigation.icon" />
                    <div class="flex absolute bottom-2">
                      <button class="w-full flex btn btn-error rounded-box">
                        <component :is="logout.icon" class="fill-current h-7 w-7" />
                        <span class="ml-2">{{ logout.title }}</span>
                      </button>
                    </div>
                  </div>
                  <!-- /End replace -->
                </div>
              </div>
            </div>
          </TransitionChild>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>

<script lang="ts">
import { Dialog, DialogOverlay, DialogTitle, TransitionChild, TransitionRoot } from '@headlessui/vue'
import { ChevronDoubleLeftIcon } from '@heroicons/vue/solid'
import { defineComponent } from 'vue'

import LogoutIcon from '../components/icons/LogoutIcon.vue'
import { navigations } from '../core/navigation'
import TheSidebarLink from './TheSidebarLink.vue'

const logout = {
  title: 'Logout',
  icon: LogoutIcon,
}
export default defineComponent({
  name: 'TheNavbarSlide',
  components: { TheSidebarLink, Dialog, DialogOverlay, DialogTitle, TransitionChild, TransitionRoot, ChevronDoubleLeftIcon },
  props: {
    open: {
      type: Boolean,
      required: true,
    },
  },
  emits: ['onClose'],
  setup(_, { emit }) {
    const onClick = () => emit('onClose')

    return {
      onClick,
      navigations,
      logout
    }
  },
})
</script>
