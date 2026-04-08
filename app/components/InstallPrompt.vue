<script setup>
const { $pwa } = useNuxtApp()

const installApp = () => {
    $pwa?.install()
}
</script>

<template>
    <button @click="installApp">
        Install App
    </button>
</template>