<script setup>
import Profile from '../components/Profile.vue';
</script>

<template>
    <Profile>
        <h1>GitHub User Data</h1>
        <template v-slot:footer>
        <footer>
            Developed by <a href="https://github.com/lucsantosdev" target="_blank">@lucsantosdev</a>
        </footer>
        </template>
    </Profile>
</template>