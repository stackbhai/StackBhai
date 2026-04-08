<template>

    <div>
        <p class="font-medium">অ্যাপ ইনস্টল করুন</p>
        <p class="text-xs text-gray-500">হোম স্ক্রিনে যোগ করুন</p>
    </div>

    <button @click="installApp" class="bg-black text-white px-4 py-2 rounded-lg text-sm">
        Install
    </button>

</template>

<script setup>
import { ref, onMounted } from 'vue'

const show = ref(false)
let deferredPrompt = null

onMounted(() => {

    window.addEventListener('beforeinstallprompt', (e) => {
        e.preventDefault()
        deferredPrompt = e
        show.value = true
    })

})

const installApp = async () => {
    if (!deferredPrompt) return

    deferredPrompt.prompt()

    const { outcome } = await deferredPrompt.userChoice

    console.log('Install result:', outcome)

    deferredPrompt = null
    show.value = false
}
</script>