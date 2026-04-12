<script setup>
const { $pwa } = useNuxtApp();

const installApp = () => {
  $pwa?.install();
};
</script>

<template>
  <Button variant="outline" class="mt-12" @click="installApp">
    অ্যাপ ইন্সটল করুন <Icon name="hugeicons:download-04" />
  </Button>
</template>
