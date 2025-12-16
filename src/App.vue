<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Chat from './components/Chat.vue'
import Header from './components/Header.vue'
import { FwbNavbar, FwbNavbarCollapse, FwbNavbarLink } from 'flowbite-vue';
</script>

<template>
  <header>
    <FwbNavbar>
      <template #default="{isShowMenu}">
        <FwbNavbarCollapse :is-show-menu="isShowMenu">
          <FwbNavbarLink is-active link="#">
            <RouterLink to="/">Home</RouterLink>
          </FwbNavbarLink>
          <FwbNavbarLink link="/chat">
            <RouterLink to="/chat">Chat</RouterLink>
          </FwbNavbarLink>
        </FwbNavbarCollapse>
      </template>
    </FwbNavbar>
  </header>

  <main>
    <RouterView />
  </main>
</template>
