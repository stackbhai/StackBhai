<template>
    <div class="min-h-screen bg-white px-4 py-5">

        <!-- Header -->
        <div class="flex items-center justify-between mb-6">
            <div>
                <h1 class="text-xl font-semibold">ড্যাশবোর্ড</h1>
                <p class="text-sm text-gray-500">স্বাগতম, {{ user.name }}</p>
            </div>

            <div class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center">
                <Icon name="mdi:account" class="text-gray-600 text-xl" />
            </div>
        </div>

        <!-- Stats -->
        <div class="grid grid-cols-2 gap-4 mb-6">

            <div class="bg-white border rounded-2xl p-4 shadow-sm flex items-center gap-3">
                <div class="bg-gray-100 p-2 rounded-lg">
                    <Icon name="mdi:book-open-page-variant" class="text-black text-xl" />
                </div>
                <div>
                    <p class="text-xs text-gray-500">মোট কোর্স</p>
                    <h2 class="text-lg font-semibold">{{ stats.totalCourses }}</h2>
                </div>
            </div>

            <div class="bg-white border rounded-2xl p-4 shadow-sm flex items-center gap-3">
                <div class="bg-gray-100 p-2 rounded-lg">
                    <Icon name="mdi:check-circle" class="text-black text-xl" />
                </div>
                <div>
                    <p class="text-xs text-gray-500">সম্পন্ন</p>
                    <h2 class="text-lg font-semibold">{{ stats.completedCourses }}</h2>
                </div>
            </div>

        </div>

        <!-- Continue Learning -->
        <div v-if="continueCourse" class="mb-6">

            <div class="flex items-center justify-between mb-2">
                <h2 class="text-lg font-medium">চালিয়ে যান</h2>
                <Icon name="mdi:arrow-right" class="text-gray-400" />
            </div>

            <div class="bg-white border rounded-2xl p-4 shadow-sm">

                <h3 class="font-medium mb-2">{{ continueCourse.title }}</h3>

                <div class="flex items-center gap-2 text-xs text-gray-500 mb-2">
                    <Icon name="mdi:play-circle-outline" />
                    <span>{{ continueCourse.progress }}% সম্পন্ন</span>
                </div>

                <!-- Progress -->
                <div class="w-full bg-gray-200 rounded-full h-2 mb-3">
                    <div class="bg-black h-2 rounded-full transition-all"
                        :style="{ width: continueCourse.progress + '%' }"></div>
                </div>

                <button
                    class="w-full bg-black text-white py-2 rounded-xl text-sm flex items-center justify-center gap-2">
                    <Icon name="mdi:play" />
                    চালিয়ে যান
                </button>

            </div>
        </div>

        <!-- Courses -->
        <div>

            <div class="flex items-center justify-between mb-3">
                <h2 class="text-lg font-medium">আমার কোর্স</h2>
                <span class="text-xs text-gray-400">সব দেখুন</span>
            </div>

            <div class="space-y-4">

                <div v-for="course in courses" :key="course.id" class="bg-white border rounded-2xl p-4 shadow-sm">

                    <div class="flex items-center justify-between mb-2">
                        <h3 class="font-medium text-sm">{{ course.title }}</h3>
                        <Icon name="mdi:chevron-right" class="text-gray-400" />
                    </div>

                    <div class="flex items-center gap-2 text-xs text-gray-500 mb-2">
                        <Icon name="mdi:clock-outline" />
                        <span>{{ course.progress }}% সম্পন্ন</span>
                    </div>

                    <!-- Progress -->
                    <div class="w-full bg-gray-200 rounded-full h-2 mb-3">
                        <div class="bg-black h-2 rounded-full transition-all" :style="{ width: course.progress + '%' }">
                        </div>
                    </div>

                    <button class="w-full border py-2 rounded-xl text-sm flex items-center justify-center gap-2">
                        <Icon name="mdi:eye-outline" />
                        কোর্স দেখুন
                    </button>

                </div>

            </div>

        </div>

    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const user = ref({
    name: 'শিক্ষার্থী'
})

const stats = ref({
    totalCourses: 0,
    completedCourses: 0
})

const courses = ref([])
const continueCourse = ref(null)

onMounted(() => {
    stats.value = {
        totalCourses: 5,
        completedCourses: 2
    }

    courses.value = [
        { id: 1, title: 'Laravel API কোর্স', progress: 60 },
        { id: 2, title: 'NuxtJS Frontend', progress: 30 }
    ]

    continueCourse.value = courses.value[0]
})
</script>