<template>
    <div>
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
.hamburger {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 50px;
    height: 50px;
    background: transparent;
    border: 2px solid black;
    border-radius: 5px;
    cursor: pointer;
    position: absolute;
    top: 20px;
    right: 20px;
}

.hamburger-line {
    width: 100%;
    height: 3px;
    background: black;
    transition: all 0.3s ease;
}

.rotate {
    transform: rotate(45deg);
}

.rotate-back {
    transform: rotate(-45deg);
}

.move-up {
    position: relative;
    top: -9px;
}

.move-down {
    position: relative;
    top: 9px;
}

.fade-out {
    opacity: 0;
}

.menu {
    list-style-type: none;
    padding: 0;
    position: absolute;
    top: 60px;
    right: 10px;
    background: white;
    border: 1px solid black;
    border-radius: 5px;
    padding: 20px;
}

.menu li {
    margin-bottom: 10px;
}
</style>