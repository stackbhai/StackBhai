<script setup lang="ts">
const videoId = "dQw4w9WgXcQ" // 👉 replace with your YouTube video ID
import {
    Accordion,
    AccordionItem,
    AccordionTrigger,
    AccordionContent
} from "@/components/ui/accordion"

import { Card } from "@/components/ui/card"
</script>

<template>
    <section class="py-16 px-6">
        <div class="max-w-6xl mx-auto grid lg:grid-cols-2 gap-4 items-center">

            <!-- LEFT CONTENT -->
            <div>
                <!-- LIVE BADGE -->
                <span class="text-xs bg-black/70 text-white px-3 py-1 rounded-full">
                    🔴 লাইভ কোর্স
                </span>

                <!-- TITLE -->
                <h1 class="text-3xl font-bold mt-2 leading-snug">
                    Full Stack Web Development with JavaScript (MERN) & AI
                </h1>

                <!-- RATING -->
                <div class="flex items-center gap-2 text-sm mb-4">
                    <span class="text-green-600 font-semibold">4.8 ★</span>
                    <span class="text-gray-500">(313 Ratings)</span>
                </div>

                <!-- DESCRIPTION -->
                <p class="text-gray-600 text-sm leading-relaxed">
                    ০ থেকে শুরু করে ফুল স্ট্যাক ডেভেলপার হওয়ার কমপ্লিট গাইডলাইন। HTML, CSS, Bootstrap,
                    Tailwind, JavaScript, Node.js, Express, MongoDB, React সহ সবকিছু শেখানো হবে প্রজেক্টের মাধ্যমে।
                </p>
                <p class="text-gray-600 text-sm leading-relaxed">
                    ০ থেকে শুরু করে ফুল স্ট্যাক ডেভেলপার হওয়ার কমপ্লিট গাইডলাইন। HTML, CSS, Bootstrap,
                    Tailwind, JavaScript, Node.js, Express, MongoDB, React সহ সবকিছু শেখানো হবে প্রজেক্টের মাধ্যমে।
                </p>
                <!-- PRICE -->
                <div class="flex items-center gap-4 my-2">
                    <span class="text-2xl font-bold">৳৬৬,৩৬৩</span>
                    <span class="text-gray-400 line-through">৳৮৮,৫০০</span>
                </div>

                <!-- CTA -->
                <div class="flex items-center gap-4 mb-2">
                    <button class="bg-yellow-400 hover:bg-yellow-500 px-6 py-3 rounded-lg font-medium">
                        ব্যাচে ভর্তি হন →
                    </button>
                </div>

                <!-- INFO TAGS -->
                <div class="flex flex-wrap gap-3 text-xs text-gray-600">
                    <span class="border px-3 py-1 rounded">📘 ৮০+ লাইভ ক্লাস</span>
                    <span class="border px-3 py-1 rounded">📂 ২৫+ প্রজেক্ট</span>
                    <span class="border px-3 py-1 rounded">🎥 রেকর্ডেড ভিডিও</span>
                </div>
            </div>

            <!-- RIGHT VIDEO -->
            <div class="relative">

                <!-- VIDEO CARD -->
                <div class="rounded-xl overflow-hidden shadow-lg border bg-black">

                    <!-- TOP BAR -->
                    <div
                        class="bg-gradient-to-r from-orange-500 to-red-500 text-white text-sm px-4 py-2 flex items-center gap-2">
                        ▶️ ফ্রি করে দেখে নিন কোর্সের ডেমো ক্লাস
                    </div>

                    <!-- YOUTUBE EMBED -->
                    <div class="aspect-video">
                        <iframe class="w-full h-full" :src="`https://www.youtube.com/embed/${videoId}`"
                            title="Course Demo" frameborder="0"
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                            allowfullscreen></iframe>
                    </div>

                </div>

            </div>
        </div>
        <div class="bg-white border rounded-xl mt-10">
            <div class="grid grid-cols-2 md:grid-cols-5 divide-x text-sm text-gray-700">

                <!-- Batch Start -->
                <div class="p-4 flex items-center gap-2">
                    <span>📅</span>
                    <div>
                        <p class="text-xs text-gray-500">ব্যাচ শুরু</p>
                        <p class="font-medium">বৃহস্পতিবার ৩০ এপ্রিল</p>
                    </div>
                </div>

                <!-- Live Class -->
                <div class="p-4 flex items-center gap-2">
                    <span>🕘</span>
                    <div>
                        <p class="text-xs text-gray-500">লাইভ ক্লাস</p>
                        <p class="font-medium">রাত ৯:০০ - ১০:৩০ (শনি,বুধ)</p>
                    </div>
                </div>

                <!-- Practice Class -->
                <div class="p-4 flex items-center gap-2">
                    <span>📆</span>
                    <div>
                        <p class="text-xs text-gray-500">ম্যারাথন ক্লাস</p>
                        <p class="font-medium">রাত ৯:০০ - ১০:০০ (রবি,মঙ্গল,বৃহ)</p>
                    </div>
                </div>

                <!-- Seats -->
                <div class="p-4 flex items-center gap-2">
                    <span>💺</span>
                    <div>
                        <p class="text-xs text-gray-500">সিট বাকি</p>
                        <p class="font-medium">২৩ টি</p>
                    </div>
                </div>

                <!-- Running Batch -->
                <div class="p-4 flex items-center gap-2">
                    <span>🎓</span>
                    <div>
                        <p class="text-xs text-gray-500">চলমান ব্যাচ</p>
                        <p class="font-medium">১৭তম ব্যাচ</p>
                    </div>
                </div>

            </div>
        </div>
    </section>
    <section class="sticky top-16 border-y py-2 w-full bg-white">
        <div class="w-full flex items-center justify-center gap-8 text-sm">
            <NuxtLink to="#curriculum">কারিকুলাম</NuxtLink>
            <NuxtLink to="#course-content">কোর্সে আপনি পাচ্ছেন</NuxtLink>
            <NuxtLink to="#projects">প্রজেক্টসমুহ</NuxtLink>
            <NuxtLink to="#who-for">কোর্সটি যাদের জন্য</NuxtLink>
            <NuxtLink to="#reviews">রিভিউ</NuxtLink>
            <NuxtLink to="#faq">FAQ</NuxtLink>
            <NuxtLink to="#payment">পেমেন্ট</NuxtLink>
        </div>
    </section>
    <section class="py-12 bg-white">
        <div class="max-w-6xl mx-auto px-4">

            <!-- Title -->
            <div class="text-center mb-10">
                <h2 class="text-3xl font-bold text-gray-900 relative inline-block">
                    কোর্স আপনি পাচ্ছেন
                    <span class="block h-1 bg-yellow-400 mt-2 w-24 mx-auto rounded"></span>
                </h2>
            </div>

            <!-- Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 divide-y sm:divide-y-0 sm:divide-x">

                <!-- Item -->
                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">📅</div>
                    <h3 class="font-semibold text-lg mb-2">৮ মাসের গাইডেড জার্নি</h3>
                    <p class="text-gray-600 text-sm">
                        একদম বিগিনার ফ্রেন্ডলি ওয়েতে আপডেটেড কারিকুলাম
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">🔴</div>
                    <h3 class="font-semibold text-lg mb-2">৮৪টি লাইভ ক্লাস</h3>
                    <p class="text-gray-600 text-sm">
                        লাইভ এক্সপেরিয়েন্সে কোড শিখুন লাইভে
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0">
                    <div class="text-3xl mb-3">⚙️</div>
                    <h3 class="font-semibold text-lg mb-2">২ টি ইন্ডাস্ট্রি স্ট্যান্ডার্ড প্রজেক্ট</h3>
                    <p class="text-gray-600 text-sm">
                        ইন্ডাস্ট্রি স্ট্যান্ডার্ড প্রজেক্ট ও টিম প্রজেক্ট
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">🎓</div>
                    <h3 class="font-semibold text-lg mb-2">৮ টি প্র্যাকটিস প্রজেক্ট</h3>
                    <p class="text-gray-600 text-sm">
                        যা শিখবেন তা দিয়ে করে ফেলুন প্র্যাকটিস প্রজেক্ট
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">🎥</div>
                    <h3 class="font-semibold text-lg mb-2">৪০০+ রেকর্ডেড ভিডিও</h3>
                    <p class="text-gray-600 text-sm">
                        আপডেটেড রেকর্ডেড ভিডিও থাকবে রেফারেন্স হিসেবে
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0">
                    <div class="text-3xl mb-3">📈</div>
                    <h3 class="font-semibold text-lg mb-2">প্রোগ্রেস ট্র্যাকিং</h3>
                    <p class="text-gray-600 text-sm">
                        নিজের প্রোগ্রেস ট্র্যাক করে এগিয়ে যান
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">👥</div>
                    <h3 class="font-semibold text-lg mb-2">কমিউনিটি সাপোর্ট</h3>
                    <p class="text-gray-600 text-sm">
                        থ্রু প্রজেক্ট কমিউনিটির সাথে লার্নিং
                    </p>
                </div>

                <div class="p-6 text-center border-b sm:border-b-0 lg:border-r">
                    <div class="text-3xl mb-3">⏳</div>
                    <h3 class="font-semibold text-lg mb-2">লাইফটাইম এক্সেস</h3>
                    <p class="text-gray-600 text-sm">
                        ভিডিও, রিসোর্স এবং ক্লাস রেকর্ডিং
                    </p>
                </div>

                <div class="p-6 text-center">
                    <div class="text-3xl mb-3">💼</div>
                    <h3 class="font-semibold text-lg mb-2">জব মার্কেট গাইডলাইন</h3>
                    <p class="text-gray-600 text-sm">
                        ইন্ডাস্ট্রিতে জব পেতে প্রয়োজনীয় গাইড
                    </p>
                </div>

            </div>
        </div>
    </section>
    <section id="curriculum" class="py-12">
        <div class="max-w-5xl mx-auto px-4">

            <!-- Title -->
            <div class="text-center mb-10">
                <h2 class="text-3xl font-bold">
                    কোর্স কারিকুলাম
                </h2>
                <p class="text-muted-foreground mt-2">
                    ধাপে ধাপে WordPress Web Development শিখুন
                </p>
            </div>

            <!-- Accordion -->
            <Accordion type="single" collapsible class="w-full grid grid-cols-2 gap-2">

                <!-- Module 1 -->
                <AccordionItem value="item-1">
                    <Card class="py-0">
                        <AccordionTrigger class="px-6 text-lg font-semibold">
                            ১. ওয়েব ডেভেলপমেন্ট বেসিক
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>HTML, CSS এর বেসিক ধারণা</li>
                                <li>Web structure কিভাবে কাজ করে</li>
                                <li>Browser rendering বুঝা</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 2 -->
                <AccordionItem value="item-2">
                    <Card class="py-0">
                        <AccordionTrigger class="px-6 text-lg font-semibold">
                            ২. WordPress পরিচিতি
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>WordPress কি এবং কেন ব্যবহার করা হয়</li>
                                <li>WordPress.com vs WordPress.org</li>
                                <li>Local server setup (XAMPP/WAMP)</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 3 -->
                <AccordionItem value="item-3">
                    <Card>
                        <AccordionTrigger class="px-6 py-4 text-lg font-semibold">
                            ৩. থিম ডেভেলপমেন্ট
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>WordPress theme structure</li>
                                <li>Custom theme তৈরি</li>
                                <li>Template hierarchy</li>
                                <li>Header, Footer, Sidebar তৈরি</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 4 -->
                <AccordionItem value="item-4">
                    <Card>
                        <AccordionTrigger class="px-6 py-4 text-lg font-semibold">
                            ৪. পেজ বিল্ডার ও Elementor
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>Elementor ব্যবহার</li>
                                <li>Drag & Drop design</li>
                                <li>Responsive layout তৈরি</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 5 -->
                <AccordionItem value="item-5">
                    <Card>
                        <AccordionTrigger class="px-6 py-4 text-lg font-semibold">
                            ৫. প্লাগইন ডেভেলপমেন্ট
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>Plugin structure বোঝা</li>
                                <li>Custom plugin তৈরি</li>
                                <li>Hooks & Filters ব্যবহার</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 6 -->
                <AccordionItem value="item-6">
                    <Card>
                        <AccordionTrigger class="px-6 py-4 text-lg font-semibold">
                            ৬. WooCommerce (E-commerce)
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>Online store setup</li>
                                <li>Product management</li>
                                <li>Payment gateway integration</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

                <!-- Module 7 -->
                <AccordionItem value="item-7">
                    <Card>
                        <AccordionTrigger class="px-6 py-4 text-lg font-semibold">
                            ৭. ডিপ্লয়মেন্ট ও লাইভ করা
                        </AccordionTrigger>
                        <AccordionContent class="px-6 pb-6 space-y-2 text-sm text-muted-foreground">
                            <ul class="list-disc pl-5 space-y-1">
                                <li>Hosting setup</li>
                                <li>Domain connection</li>
                                <li>Website live করা</li>
                            </ul>
                        </AccordionContent>
                    </Card>
                </AccordionItem>

            </Accordion>
        </div>
    </section>
    <section class="bg-white py-12">
        <div class="max-w-6xl mx-auto px-4">

            <!-- Heading -->
            <div class="text-center mb-10">
                <h2 class="text-2xl md:text-3xl font-bold">
                    যেসব ফিচার নিয়ে প্রোজেক্ট করা হয়েছে
                </h2>
            </div>

            <!-- Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">

                <!-- Card 1 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        ফুল স্ট্যাক ই-কমার্স প্রোজেক্ট
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

                <!-- Card 2 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        ফুল স্ট্যাক ইনভেন্টরি ম্যানেজমেন্ট সিস্টেম
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

                <!-- Card 3 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        টাস্ক ম্যানেজার প্রোজেক্ট
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

                <!-- Card 4 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        ফুল স্ট্যাক বিজনেস টেবিল প্রোজেক্ট
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

                <!-- Card 5 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        QR কোড জেনারেটর
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

                <!-- Card 6 -->
                <div class="flex items-center justify-between bg-gray-900 text-white rounded-xl overflow-hidden p-4">
                    <h3 class="text-lg font-semibold w-1/2">
                        ই-কমার্স কাট প্রোজেক্ট
                    </h3>
                    <img src="https://placehold.co/300x200" class="w-1/2 rounded-lg object-cover" />
                </div>

            </div>
        </div>
    </section>
    <section class="py-14 bg-gray-50">
        <div class="max-w-5xl mx-auto px-4">

            <!-- Heading -->
            <div class="text-center mb-12">
                <h2 class="text-2xl md:text-3xl font-semibold text-gray-800">
                    কোর্সটি কার জন্য
                </h2>
                <p class="text-gray-500 mt-2 text-sm">
                    নিচের যে কোনো ক্যাটাগরিতে পড়লে এই কোর্সটি আপনার জন্য পারফেক্ট
                </p>
            </div>

            <!-- Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-blue-600 text-xl mb-3">💻</div>
                    <h3 class="font-medium text-gray-800 mb-1">Beginner</h3>
                    <p class="text-sm text-gray-500">
                        যারা একদম শুরু থেকে web development শিখতে চান।
                    </p>
                </div>

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-green-600 text-xl mb-3">🚀</div>
                    <h3 class="font-medium text-gray-800 mb-1">Freelancer</h3>
                    <p class="text-sm text-gray-500">
                        যারা Fiverr / Upwork এ কাজ শুরু করতে চান।
                    </p>
                </div>

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-purple-600 text-xl mb-3">🧠</div>
                    <h3 class="font-medium text-gray-800 mb-1">Intermediate</h3>
                    <p class="text-sm text-gray-500">
                        যারা basic জানেন এবং real project করতে চান।
                    </p>
                </div>

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-yellow-600 text-xl mb-3">📈</div>
                    <h3 class="font-medium text-gray-800 mb-1">Job Seeker</h3>
                    <p class="text-sm text-gray-500">
                        যারা portfolio বানিয়ে job পেতে চান।
                    </p>
                </div>

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-red-600 text-xl mb-3">⚡</div>
                    <h3 class="font-medium text-gray-800 mb-1">Startup Founder</h3>
                    <p class="text-sm text-gray-500">
                        যারা নিজের product বা startup build করতে চান।
                    </p>
                </div>

                <!-- Card -->
                <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-all duration-300">
                    <div class="text-indigo-600 text-xl mb-3">🎯</div>
                    <h3 class="font-medium text-gray-800 mb-1">Skill Upgrade</h3>
                    <p class="text-sm text-gray-500">
                        যারা skill improve করে advanced level এ যেতে চান।
                    </p>
                </div>

            </div>
        </div>
    </section>
    <section class="py-12 bg-gray-50">
        <div class="max-w-3xl mx-auto px-4">

            <!-- Heading -->
            <div class="text-center mb-8">
                <h2 class="text-2xl md:text-3xl font-bold text-gray-800">
                    প্রায়শই জিজ্ঞাসিত প্রশ্ন (FAQ)
                </h2>
                <p class="text-gray-500 mt-2">
                    আপনার প্রশ্নের উত্তর এখানে পেতে পারেন
                </p>
            </div>

            <!-- Accordion -->
            <Accordion type="single" collapsible class="w-full space-y-4">

                <!-- Item 1 -->
                <AccordionItem value="item-1" class="bg-white rounded-lg border px-4">
                    <AccordionTrigger class="text-left font-medium">
                        এই কোর্সটি কার জন্য?
                    </AccordionTrigger>
                    <AccordionContent class="text-gray-600 text-sm">
                        এই কোর্সটি beginners, freelancers এবং যারা real-world project করতে চান তাদের জন্য।
                    </AccordionContent>
                </AccordionItem>

                <!-- Item 2 -->
                <AccordionItem value="item-2" class="bg-white rounded-lg border px-4">
                    <AccordionTrigger class="text-left font-medium">
                        কোর্সটি করতে কি আগে কোনো experience লাগবে?
                    </AccordionTrigger>
                    <AccordionContent class="text-gray-600 text-sm">
                        না, basic computer knowledge থাকলেই আপনি এই কোর্স শুরু করতে পারবেন।
                    </AccordionContent>
                </AccordionItem>

                <!-- Item 3 -->
                <AccordionItem value="item-3" class="bg-white rounded-lg border px-4">
                    <AccordionTrigger class="text-left font-medium">
                        এই কোর্সে কি কি শিখানো হবে?
                    </AccordionTrigger>
                    <AccordionContent class="text-gray-600 text-sm">
                        HTML, CSS, Tailwind, Vue/Nuxt, Laravel এবং real project-based কাজ শেখানো হবে।
                    </AccordionContent>
                </AccordionItem>

                <!-- Item 4 -->
                <AccordionItem value="item-4" class="bg-white rounded-lg border px-4">
                    <AccordionTrigger class="text-left font-medium">
                        কোর্স শেষে কি আমি income করতে পারবো?
                    </AccordionTrigger>
                    <AccordionContent class="text-gray-600 text-sm">
                        হ্যাঁ, আপনি Fiverr/Upwork এ কাজ করতে পারবেন এবং client project নিতে পারবেন।
                    </AccordionContent>
                </AccordionItem>

            </Accordion>

        </div>
    </section>
    <section class="bg-black text-white py-16">
        <div class="max-w-6xl mx-auto px-4 space-y-20">

            <!-- Item 1 -->
            <div class="grid md:grid-cols-2 gap-10 items-center">

                <!-- Text -->
                <div>
                    <div
                        class="w-10 h-10 flex items-center justify-center bg-white text-black rounded-full mb-4 font-bold">
                        ১
                    </div>
                    <h3 class="text-xl font-semibold mb-3">
                        ধাপে ধাপে প্রোজেক্ট ভিত্তিক শেখানো
                    </h3>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        একদম শুরু থেকে ধাপে ধাপে real-world project এর মাধ্যমে শেখানো হবে।
                        আপনি শুধু theory না, বাস্তব কাজ শিখবেন।
                    </p>
                </div>

                <!-- Image -->
                <div>
                    <img src="https://placehold.co/400x250/000000/FFFFFF" class="rounded-xl border border-gray-700">
                </div>
            </div>

            <!-- Item 2 -->
            <div class="grid md:grid-cols-2 gap-10 items-center">

                <!-- Image -->
                <div class="md:order-1 order-2">
                    <img src="https://placehold.co/400x250/000000/FFFFFF" class="rounded-xl border border-gray-700">
                </div>

                <!-- Text -->
                <div class="md:order-2 order-1">
                    <div
                        class="w-10 h-10 flex items-center justify-center bg-white text-black rounded-full mb-4 font-bold">
                        ২
                    </div>
                    <h3 class="text-xl font-semibold mb-3">
                        প্র্যাকটিসের মাধ্যমে শেখার সুযোগ
                    </h3>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        প্রতিটি লেসনের পরে থাকবে প্র্যাকটিস টাস্ক যাতে আপনি নিজে নিজে কাজ করতে পারেন।
                    </p>
                </div>
            </div>

            <!-- Item 3 -->
            <div class="grid md:grid-cols-2 gap-10 items-center">

                <!-- Text -->
                <div>
                    <div
                        class="w-10 h-10 flex items-center justify-center bg-white text-black rounded-full mb-4 font-bold">
                        ৩
                    </div>
                    <h3 class="text-xl font-semibold mb-3">
                        সমস্যা সমাধান গাইডলাইন
                    </h3>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        আপনি কোথাও আটকে গেলে solution guide পাবেন এবং বুঝতে পারবেন কিভাবে solve করতে হয়।
                    </p>
                </div>

                <!-- Image -->
                <div>
                    <img src="https://placehold.co/400x250/000000/FFFFFF" class="rounded-xl border border-gray-700">
                </div>
            </div>

            <!-- Item 4 -->
            <div class="grid md:grid-cols-2 gap-10 items-center">

                <!-- Image -->
                <div class="md:order-1 order-2">
                    <img src="https://placehold.co/400x250/000000/FFFFFF" class="rounded-xl border border-gray-700">
                </div>

                <!-- Text -->
                <div class="md:order-2 order-1">
                    <div
                        class="w-10 h-10 flex items-center justify-center bg-white text-black rounded-full mb-4 font-bold">
                        ৪
                    </div>
                    <h3 class="text-xl font-semibold mb-3">
                        লাইফটাইম সাপোর্ট
                    </h3>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        কোর্স শেষ হলেও আপনি পাবেন লাইফটাইম সাপোর্ট এবং আপডেট।
                    </p>
                </div>
            </div>

        </div>
    </section>
</template>