<template>
    <section class="py-16 bg-black text-white overflow-hidden">

        <!-- Heading -->
        <div class="text-center mb-10">
            <h2 class="text-2xl md:text-3xl font-semibold">
                আমাদের স্টুডেন্টদের রিভিউ
            </h2>
            <p class="text-gray-400 text-sm mt-2">
                যারা কোর্সটি করে সফল হয়েছে
            </p>
        </div>

        <!-- Row 1 (Left Scroll) -->
        <div class="relative overflow-hidden mb-6">
            <div class="flex w-max gap-6 animate-scroll-left">

                <ReviewCard v-for="i in 8" :key="'top-' + i" />
                <!-- duplicate for seamless loop -->
                <ReviewCard v-for="i in 8" :key="'top-dup-' + i" />

            </div>
        </div>

        <!-- Row 2 (Right Scroll) -->
        <div class="relative overflow-hidden">
            <div class="flex w-max gap-6 animate-scroll-right">

                <ReviewCard v-for="i in 8" :key="'bottom-' + i" />
                <ReviewCard v-for="i in 8" :key="'bottom-dup-' + i" />

            </div>
        </div>

    </section>
</template>

<script setup>
</script>