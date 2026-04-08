<template>
    <div>
        <p class="font-medium">অ্যাপ ইনস্টল করুন</p>
        <p class="text-xs text-gray-500">হোম স্ক্রিনে যোগ করুন</p>

        <button v-if="deferredPrompt" @click="installApp" class="bg-black text-white px-4 py-2 rounded-lg text-sm mt-2">
            Install
        </button>

        <p v-else class="text-xs text-gray-400 mt-2">
            Install option not available
        </p>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const deferredPrompt = ref(null)

onMounted(() => {
    window.addEventListener('beforeinstallprompt', (e) => {
        e.preventDefault()
        deferredPrompt.value = e
    })
})

const installApp = async () => {
    if (!deferredPrompt.value) return

    deferredPrompt.value.prompt()

    const { outcome } = await deferredPrompt.value.userChoice

    console.log('Install result:', outcome)

    deferredPrompt.value = null
}
</script>