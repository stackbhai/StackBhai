<template>
    <div>
        <InstallPrompt />
        <section class="text-center py-20 px-6">
            <h2 class="text-5xl font-bold leading-tight mb-6">
                শিখুন এমন স্কিল যা <br />
                <span class="bg-gradient-to-r from-black to-gray-500 text-transparent bg-clip-text">
                    ক্যারিয়ারে কাজে লাগবে
                </span>
            </h2>
            <p class="text-gray-600 max-w-2xl mx-auto mb-8">
                হাজারো শিক্ষার্থীর সাথে যোগ দিন যারা নতুন স্কিল শিখছে, ক্যারিয়ার গড়ছে এবং আমাদের কোর্সের মাধ্যমে নিজের
                লক্ষ্য পূরণ করছে। আমাদের ফ্রি কোর্সগুলো এক্সপ্লোর করুন, শিখুন এবং নিজের আয়ের সুযোগ তৈরি করুন।
            </p>
            <div class="flex justify-center gap-4">
                <NuxtLink to="/courses" class="bg-black text-white px-6 py-3 rounded-xl shadow-lg">
                    এখনই শেখা শুরু করুন
                </NuxtLink>
                <NuxtLink to="/courses" class="border px-6 py-3 rounded-xl flex items-center justify-center gap-3">
                    <span class="relative flex size-3">
                        <span
                            class="absolute inline-flex h-full w-full animate-ping rounded-full bg-gray-400 opacity-75"></span>
                        <span class="relative inline-flex size-3 rounded-full bg-gray-500"></span>
                    </span>
                    <span>লাইভ কোর্স করতে চাই</span>
                </NuxtLink>
            </div>
        </section>


        <section class="bg-white py-24">
            <div class="max-w-5xl mx-auto px-6 grid md:grid-cols-2 gap-8 items-center">

                <!-- LEFT IMAGE DESIGN -->
                <div class="relative flex justify-center">
                    <!-- FRONT IMAGE -->
                    <div
                        class="relative w-80 h-88 bg-white rounded-2xl shadow-sm border-2 border-white overflow-hidden transform -rotate-3">
                        <img src="https://placehold.co/600x400" alt="Instructor" class="w-full h-full object-cover" />
                    </div>
                </div>

                <!-- RIGHT CONTENT -->
                <div class="relative">

                    <!-- TITLE -->
                    <h2 class="text-3xl font-bold leading-tight mb-6">
                        <span class="bg-gradient-to-r from-black to-gray-500 text-transparent bg-clip-text">
                            প্রতিষ্ঠাতা সম্পর্কে
                        </span> <span class="bg-gradient-to-l from-black to-gray-500 text-transparent bg-clip-text">
                            কিছু কথা</span>
                    </h2>
                    <!-- TEXT CONTENT -->
                    <div class="">
                        <p class="text-gray-600 text-sm leading-relaxed">
                            আমি Stack Bhai। ২০২১ সাল থেকে ওয়েব ডেভেলপমেন্ট ইন্ডাস্ট্রিতে কাজ করছি এবং গত কয়েক বছরে
                            বাস্তব প্রজেক্টের মাধ্যমে অনেক অভিজ্ঞতা অর্জন করেছি। আমার এই জার্নিতে আমি বুঝেছি—শুধু থিওরি
                            জানলেই হয় না, বাস্তব স্কিলই আসল। তাই আমি আমার @stackbhai ইউটিউব চ্যানেলে সম্পূর্ণ ফ্রিতে
                            হাজারো শিক্ষার্থীকে শেখাচ্ছি, যাতে তারা সহজে এবং সঠিকভাবে স্কিল ডেভেলপ করতে পারে।
                        </p>

                        <p class="my-4 text-gray-600 text-sm leading-relaxed">
                            আজ আমার অনেক স্টুডেন্ট এই স্কিল ব্যবহার করে অনলাইনে আয় করছে, ফ্রিল্যান্সিং করছে এবং নিজের
                            ক্যারিয়ার গড়ে তুলছে—এটাই আমার সবচেয়ে বড় অর্জন। আমার লক্ষ্য একটাই—বাংলাদেশের প্রতিটা মানুষ
                            যেন বাস্তবমুখী স্কিল শিখে নিজের লাইফ পরিবর্তন করতে পারে। কোনো ফালতু কথা না, শুধু সেই
                            জিনিসগুলোই শেখাই যেগুলো সত্যিই কাজে লাগে এবং আপনাকে আয় করতে সাহায্য করবে।
                        </p>

                        <!-- INFO -->
                        <div>
                            <div class="space-y-1">
                                <h4 class="text-sm font-medium leading-none">
                                    Stack Bhai
                                </h4>
                                <p class="text-xs text-muted-foreground">
                                    Founder of StackBhai Platform
                                </p>
                            </div>
                            <Separator class="my-2" />
                            <div class="flex h-5 items-center space-x-4 text-sm">
                                <Icon name="hugeicons:whatsapp" />
                                <Separator orientation="vertical" />
                                <Icon name="hugeicons:facebook-02" />
                                <Separator orientation="vertical" />
                                <Icon name="hugeicons:youtube" />
                                <Separator orientation="vertical" />
                                <Icon name="hugeicons:github" />
                            </div>
                        </div>

                    </div>

                </div>

            </div>
        </section>


    </div>
</template>

<script setup lang="ts">
import { Separator } from '@/components/ui/separator'

</script>

<style scoped></style>