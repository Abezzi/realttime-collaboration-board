<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import {
  FwbFooter,
  FwbFooterCopyright,
  FwbNavbar,
  FwbNavbarCollapse,
  FwbNavbarLink,
} from 'flowbite-vue'
import { computed } from 'vue'

const route = useRoute()

const isHomeActive = computed(() => route.path === '/')
const isBoardActive = computed(() => route.path === '/board')
</script>

<template>
  <div class="flex min-h-screen flex-col bg-gray-50">
    <nav>
      <FwbNavbar>
        <template #default="{ isShowMenu }">
          <FwbNavbarCollapse :is-show-menu="isShowMenu">
            <!-- home link -->
            <FwbNavbarLink :is-active="isHomeActive" link="#">
              <RouterLink to="/">Home</RouterLink>
            </FwbNavbarLink>

            <!-- board link -->
            <FwbNavbarLink :is-active="isBoardActive" link="board">
              <RouterLink to="/board">Board</RouterLink>
            </FwbNavbarLink>
          </FwbNavbarCollapse>
        </template>
      </FwbNavbar>
    </nav>

    <main class="flex-1 flex items-center justify-center px-6 py-12 md:px-12 lg:px-24">
      <div class="w-full max-w-4xl">
        <RouterView />
      </div>
    </main>

    <footer class="mt-auto">
      <FwbFooter footer-type="socialmedia">
        <FwbFooterCopyright
          by="Alex Herrera™"
          href="www.alexherrera.cl"
          copyright-message="All Rights Reserved."
        >
        </FwbFooterCopyright>
      </FwbFooter>
    </footer>
  </div>
</template>

<style scoped>
body {
  height: 100%;
  display: flex;
  flex-direction: column;
}
main {
  flex: 1;
}
</style>
