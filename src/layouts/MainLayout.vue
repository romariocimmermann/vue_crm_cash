<template>
  <div>
    <div class="app-main-layout">
      <Navbar @clickOn="isOpen = !isOpen" />
      <Sidebar v-model="isOpen" />

      <main class="app-content" :class="{ full: !isOpen }">
        <div class="app-page">
          <router-view />
        </div>
      </main>

      <div class="fixed-action-btn">
        <router-link
          class="btn-floating btn-large blue"
          :to="{ name: 'record' }"
        >
          <i class="large material-icons">add</i>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import Navbar from "../components/Navbar";
import Sidebar from "../components/Sidebar";
export default {
  name: "MainLayout",
  data: () => ({
    isOpen: true
  }),
  components: { Navbar, Sidebar }
};
</script>
