<template>
    <div class>
        <button class="hamburger" @click="toggleMenu">
            <span class="hamburger-line" :class="{ 'rotate': isMenuOpen, 'move-down': isMenuOpen }"></span>
            <span class="hamburger-line" :class="{ 'fade-out': isMenuOpen }"></span>
            <span class="hamburger-line" :class="{ 'rotate-back': isMenuOpen, 'move-up': isMenuOpen }"></span>
        </button>

        <ul v-if="isMenuOpen" class="menu">
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/jobs">Jobs</a></li>
        </ul>
    </div>
</template>
  
<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
    data() {
        return {
            isMenuOpen: ref(false),
        };
    },
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
        },
    },
});
</script>

  
<style scoped>
@import url("~/assets/css/humburger-menu.css");
</style>