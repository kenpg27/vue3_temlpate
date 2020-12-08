<template>
    <div>
        {{ title }}
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent(() => {
    const title = 'vue_cli_test'
    return {
        title
    }
})
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
