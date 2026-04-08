<script setup lang="ts">
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import { Button } from '~/components/ui/button';
import { Card, CardContent } from '~/components/ui/card';

const freeCourses = [
    {
        title: "WordPress Web Development",
        slug: "free-wordpress-web-development-tutorial-bangla",
        description: "ওয়ার্ডপ্রেস ব্যবহার করে প্রফেশনাল, রেসপন্সিভ ও ইউজার-ফ্রেন্ডলি ওয়েবসাইট তৈরি করা শিখুন, একদম বেসিক থেকে।"
    },
    {
        title: "Vue.js Mastery",
        slug: "free-vuejs-tutorial-bangla",
        description: "Vue.js এর মাধ্যমে ডাইনামিক, দ্রুতগতির এবং মডার্ন ওয়েব অ্যাপ্লিকেশন তৈরি করার সম্পূর্ণ গাইডলাইন শিখুন।"
    }
]

const paidCourses = [
    {
        title: "Laravel Live Bootcamp",
        slug: "laravel-live",
        description: "লাইভ ক্লাসে প্রজেক্ট ভিত্তিক Laravel শেখা এবং মেন্টর সাপোর্ট। মডার্ন ওয়েব অ্যাপ্লিকেশন তৈরি করার সম্পূর্ণ গাইডলাইন শিখুন।",
        price: 1999,
        oldPrice: 3999,
        batch: "০৩",
        seats: "৩৯",
        startDate: "১৬"
    }
]
</script>

<template>
    <section class="py-20 px-6">
        <div class="max-w-6xl mx-auto">

            <!-- TITLE -->
            <h2 class="text-3xl font-bold mb-8 text-center">
                আমাদের কোর্সসমূহ
            </h2>

            <!-- TABS -->
            <Tabs default-value="free" class="w-full flex items-center justify-center">

                <TabsList class="grid grid-cols-2 mb-10 h-full">
                    <TabsTrigger value="free" class="p-3 px-8">ফ্রি কোর্স</TabsTrigger>
                    <TabsTrigger value="paid" class="p-3 px-8 space-x-1.5">
                        <span>লাইভ কোর্স</span>
                        <span class="relative flex size-3">
                            <span
                                class="absolute inline-flex h-full w-full animate-ping rounded-full bg-gray-400 opacity-75"></span>
                            <span class="relative inline-flex size-3 rounded-full bg-gray-500"></span>
                        </span>

                    </TabsTrigger>
                </TabsList>

                <!-- FREE COURSES -->
                <TabsContent value="free">
                    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
                        <Card v-for="course in freeCourses" :key="course.slug" class="py-3">
                            <CardContent class="space-y-1 px-3">
                                <NuxtImg src="https://placehold.co/600x400" class="w-full object-cover rounded" />
                                <h3 class="font-semibold mb-2 flex items-center gap-2">
                                    {{ course.title }}

                                    <span
                                        class="text-xs bg-black text-white px-2 py-1 rounded flex items-center gap-1.5">
                                        <span>ফ্রি</span>
                                    </span>
                                </h3>
                                <p class="text-sm text-gray-600 mb-4 line-clamp-2">
                                    {{ course.description }}
                                </p>

                                <NuxtLink :to="`/courses/${course.slug}`"
                                    class="text-sm w-full font-medium hover:underline bg-accent rounded">
                                    <Button class="w-full">শেখা শুরু করুন →</Button>
                                </NuxtLink>
                            </CardContent>
                        </Card>
                    </div>
                </TabsContent>

                <!-- PAID COURSES -->
                <TabsContent value="paid">
                    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
                        <Card v-for="course in paidCourses" :key="course.slug" class="py-3">
                            <CardContent class="space-y-1 px-3">
                                <!--Image-->
                                <NuxtImg src="https://placehold.co/600x400" class="w-full object-cover rounded" />

                                <!-- EXTRA INFO -->
                                <div class="text-xs text-gray-500 flex flex-row items-center justify-baseline gap-1.5">

                                    <!-- BATCH TAG -->
                                    <span class="text-xs border px-2 py-1 rounded">
                                        ব্যাচ {{ course.batch }}
                                    </span>
                                    <span class="text-xs border px-2 py-1 rounded">
                                        <Icon name="hugeicons:user" /> {{ course.seats }} সিট বাকি
                                    </span>
                                    <span class="text-xs border px-2 py-1 rounded">
                                        <Icon name="hugeicons:calendar-03" /> {{ course.startDate }} দিন বাকি
                                    </span>
                                </div>
                                <!-- TITLE + LIVE BADGE -->
                                <h3 class="font-semibold mb-2 flex items-center gap-2">
                                    {{ course.title }}

                                    <span
                                        class="text-xs bg-black text-white px-2 py-1 rounded flex items-center gap-1.5">
                                        <span>লাইভ</span>
                                        <span class="relative flex size-2.5">
                                            <span
                                                class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white/70"></span>
                                            <span class="relative inline-flex size-2 rounded-full bg-white"></span>
                                        </span>
                                    </span>
                                </h3>

                                <!-- DESCRIPTION -->
                                <p class="text-sm text-gray-600 mb-2 line-clamp-2">
                                    {{ course.description }}
                                </p>

                                <div class="flex flex-row items-center justify-between">
                                    <!-- PRICE -->
                                    <div class="flex items-center gap-3 mb-3">
                                        <span class="text-lg font-bold text-black">
                                            ৳{{ course.price }}
                                        </span>
                                        <span class="text-sm text-gray-400 line-through">
                                            ৳{{ course.oldPrice }}
                                        </span>
                                    </div>

                                    <!-- CTA -->
                                    <NuxtLink :to="`/course/${course.slug}`"
                                        class="text-sm font-medium hover:underline">
                                        বিস্তারিত →
                                    </NuxtLink>
                                </div>
                            </CardContent>
                        </Card>
                    </div>
                </TabsContent>

            </Tabs>
        </div>
    </section>
</template>