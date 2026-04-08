<template>
    <div class="min-h-screen">
        <!-- Main Container -->
        <div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-12 gap-6 p-6">

            <!-- Left Side: Video Player + Content -->
            <Card class="lg:col-span-8 space-y-6">

                <CardContent>
                    <!-- Video Player -->
                    <div class="bg-black rounded-xl overflow-hidden shadow-2xl relative">
                        <iframe width="815" height="458" src="https://www.youtube.com/embed/Pu3-2rchl9s"
                            title="কীভাবে জাপান সাম্রাজ্যের অবিশ্বাস্য উত্থান হয়েছিল | আদ্যোপান্ত | Rise of Japan’s Empire"
                            frameborder="0"
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                            referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                    </div>

                    <!-- Action Buttons -->
                    <div class="flex justify-between p-3 px-0 my-3">
                        <Button>
                            <span> ← আগের লেকচার</span>
                        </Button>

                        <Button>
                            পরের লেকচার →
                        </Button>
                    </div>

                    <div class="my-2 pb-2">
                        <h2 class="font-semibold text-2xl">ডোমেইন ও হোস্টিং কীভাবে কাজ করে</h2>
                        <p class="text-sm">এই ভিডিও এতে গিট ও গিটহাব এর দরকারি জিনিসপত্র দেখানো হয়েছে। যাতে কোর্সের মাঝে
                            আপনারা গিট ও
                            গিটহাব নিয়ে কোনো প্রকার সমস্যায় না পড়েন।</p>
                    </div>

                    <!-- Tabs -->
                    <Tabs default-value="account">
                        <TabsList class="bg-transparent space-x-6">
                            <TabsTrigger value="desc" class="p-4 px-8">
                                ভিডিও ডেসক্রিপশন
                            </TabsTrigger>
                            <TabsTrigger value="ref" class="p-4 px-8">
                                প্রয়োজনীয় রেফারেন্স
                            </TabsTrigger>
                        </TabsList>
                        <TabsContent value="desc">
                            <p class="text-xs">বেসিক থেকে শুরু করে সম্পূর্ণ প্রফেশনাল ওয়ার্ডপ্রেস ওয়েবসাইট তৈরি শেখার
                                একটি সহজ ও কার্যকর
                                কোর্স।</p>
                        </TabsContent>
                        <TabsContent value="ref">
                            <p class="text-xs">মডার্ন ফ্রন্টএন্ড ডেভেলপমেন্টের জন্য Vue.js ব্যবহার করে শক্তিশালী ও
                                ইন্টারঅ্যাকটিভ অ্যাপ
                                তৈরি শিখুন।</p>

                        </TabsContent>
                    </Tabs>
                </CardContent>
            </Card>

            <!-- Right Sidebar: Course Curriculum -->
            <div class="lg:col-span-4">
                <Card class="p-2">
                    <CardContent class="p-2">

                        <!-- Search -->
                        <div class="mb-3">
                            <Input placeholder="Search lessons..." />
                        </div>

                        <ScrollArea class="h-[600px]">

                            <Accordion type="single" collapsible class="space-y-2">

                                <AccordionItem v-for="(module, mIndex) in modules" :key="mIndex"
                                    :value="'module-' + mIndex" class="border rounded-lg px-4 ">

                                    <!-- MODULE HEADER -->
                                    <AccordionTrigger class="text-left">
                                        <div>
                                            <p class="font-semibold text-sm">
                                                {{ module.title }}
                                            </p>
                                            <p class="text-xs text-gray-500">
                                                {{ module.duration }}
                                            </p>
                                        </div>
                                    </AccordionTrigger>

                                    <!-- LESSON LIST -->
                                    <AccordionContent>
                                        <div class="space-y-2 mt-2">
                                            <div v-for="(lesson, i) in module.lessons" :key="i"
                                                class="flex items-center gap-3 px-3 py-2 rounded-lg hover:bg-gray-100 cursor-pointer transition">
                                                <!-- NUMBER -->
                                                <div
                                                    class="w-6 h-6 bg-black text-white text-xs flex items-center justify-center rounded">
                                                    {{ i + 1 }} </div> <!-- TEXT -->
                                                <div class="flex-1">
                                                    <p class="text-sm line-clamp-2"> {{ lesson.title }} </p>
                                                    <p class="text-xs text-gray-500"> {{ lesson.duration }} </p>
                                                </div>
                                            </div>
                                        </div>
                                    </AccordionContent>

                                </AccordionItem>

                            </Accordion>

                        </ScrollArea>

                    </CardContent>
                </Card>
            </div>
        </div>
    </div>
</template>

<script setup>
import { Button } from '~/components/ui/button';
import { Card, CardContent } from '~/components/ui/card';
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import { Input } from '~/components/ui/input';
import { ScrollArea } from '~/components/ui/scroll-area';
import {
    Accordion,
    AccordionContent,
    AccordionItem,
    AccordionTrigger,
} from '@/components/ui/accordion';
import { Stepper, StepperDescription, StepperItem, StepperSeparator, StepperTitle, StepperTrigger } from '@/components/ui/stepper'
import { Check, Circle, Dot } from 'lucide-vue-next'
const modules = [
    {
        title: "মডিউল ১ - ওয়ার্ডপ্রেস পরিচিতি",
        duration: "১ ঘন্টা ৩০ মিনিট • ৪টি ভিডিও",
        lessons: [
            { title: "ওয়ার্ডপ্রেস কী & এটি কীভাবে কাজ করে", duration: "১০:০০ মিনিট" },
            { title: "WordPress.com বনাম WordPress.org", duration: "০৮:০০ মিনিট" },
            { title: "ব্যবহার (ব্লগ, ব্যবসা, ই-কমার্স)", duration: "০৭:০০ মিনিট" },
            { title: "ওয়ার্ডপ্রেস ইনস্টলেশন (লোকাল + লাইভ)", duration: "২০:০০ মিনিট" },
            { title: "ড্যাশবোর্ড ওভারভিউ", duration: "১৫:০০ মিনিট" },
        ],
    },
    {
        title: "মডিউল ২ - ডোমেইন ও হোস্টিং সেটআপ",
        duration: "২ ঘন্টা • ৪টি ভিডিও",
        lessons: [
            { title: "ডোমেইন ও হোস্টিং কীভাবে কাজ করে", duration: "১২:০০ মিনিট" },
            { title: "ডোমেইন ও হোস্টিং কেনা", duration: "১০:০০" },
            { title: "ডোমেইনকে হোস্টের সাথে সংযোগ করা", duration: "১৫:০০" },
            { title: "cPanel ব্যবহার করে ওয়ার্ডপ্রেস ইনস্টল করা", duration: "২০:০০" },
            { title: "SSL & নিরাপত্তার বেসিকস", duration: "১০:০০" },
        ],
    },
    {
        title: "মডিউল ৩ - ড্যাশবোর্ড মাস্টারি",
        duration: "২ ঘন্টা ৩০ মিনিট • ৪টি ভিডিও",
        lessons: [
            { title: "পোস্ট বনাম পেজ", duration: "১০:০০" },
            { title: "ক্যাটাগরি & ট্যাগ", duration: "০৮:০০" },
            { title: "মিডিয়া লাইব্রেরি", duration: "১২:০০" },
            { title: "মেনু & নেভিগেশন", duration: "১৫:০০" },
            { title: "ইউজার রোলস & পারমিশন", duration: "১০:০০" },
        ],
    },
    {
        title: "মডিউল ৪ - থিম & ডিজাইন",
        duration: "৩ ঘন্টা • ৪টি ভিডিও",
        lessons: [
            { title: "থিম কী", duration: "০৮:০০" },
            { title: "ফ্রি & প্রিমিয়াম থিম ইনস্টল করা", duration: "১৫:০০" },
            { title: "থিম সেটিংস কাস্টমাইজ করা", duration: "২০:০০" },
            { title: "থিম কাস্টমাইজার ব্যবহার করা", duration: "১৮:০০" },
            { title: "বিভিন্ন ব্যবহার অনুযায়ী সেরা থিম", duration: "১০:০০" },
        ],
    },
    {
        title: "মডিউল ৫ - পেজ বিল্ডার (Elementor)",
        duration: "৪ ঘন্টা • ৪টি ভিডিও",
        lessons: [
            { title: "Elementor পরিচিতি", duration: "১০:০০" },
            { title: "প্রথম পেজ তৈরি করা", duration: "২৫:০০" },
            { title: "সেকশন, কলাম & উইজেট", duration: "২০:০০" },
            { title: "রেসপন্সিভ ডিজাইন", duration: "১৮:০০" },
            { title: "ল্যান্ডিং পেজ ডিজাইন", duration: "৩০:০০" },
        ],
    },
    {
        title: "মডিউল ৬ - প্রয়োজনীয় প্লাগইন",
        duration: "৩ ঘন্টা • ৪টি ভিডিও",
        lessons: [
            { title: "প্লাগইন কী", duration: "০৮:০০" },
            { title: "মাস্ট-হ্যাভ প্লাগইন লিস্ট", duration: "১২:০০" },
            { title: "SEO প্লাগইন সেটআপ (RankMath/Yoast)", duration: "২০:০০" },
            { title: "নিরাপত্তা প্লাগইন সেটআপ", duration: "১৫:০০" },
            { title: "ব্যাকআপ & পারফরম্যান্স প্লাগইন", duration: "১৮:০০" },
        ],
    },
    {
        title: "মডিউল ৭ - ব্লগ ওয়েবসাইট প্রজেক্ট",
        duration: "৩ ঘন্টা",
        lessons: [
            { title: "ব্লগ স্ট্রাকচার পরিকল্পনা", duration: "১০:০০" },
            { title: "হোমপেজ ডিজাইন", duration: "৩০:০০" },
            { title: "ব্লগ পোস্ট তৈরি", duration: "২০:০০" },
            { title: "SEO জন্য অপ্টিমাইজ করা", duration: "২৫:০০" },
        ],
    },
    {
        title: "মডিউল ৮ - বিজনেস ওয়েবসাইট প্রজেক্ট",
        duration: "৪ ঘন্টা",
        lessons: [
            { title: "হোমপেজ ডিজাইন", duration: "৩০:০০" },
            { title: "About & Services পেজ", duration: "২০:০০" },
            { title: "Contact ফর্ম সেটআপ", duration: "১৫:০০" },
            { title: "স্পিড অপ্টিমাইজেশন", duration: "২৫:০০" },
        ],
    },
    {
        title: "মডিউল ৯ - WooCommerce স্টোর",
        duration: "৫ ঘন্টা",
        lessons: [
            { title: "WooCommerce ইনস্টল করা", duration: "১৫:০০" },
            { title: "প্রোডাক্ট যোগ করা", duration: "২৫:০০" },
            { title: "পেমেন্ট গেটওয়ে সেটআপ", duration: "২০:০০" },
            { title: "শিপিং & ট্যাক্স", duration: "১৫:০০" },
            { title: "অর্ডার ম্যানেজমেন্ট", duration: "২০:০০" },
        ],
    },
    {
        title: "মডিউল ১০ - অ্যাডভান্সড & ফ্রিল্যান্সিং",
        duration: "৩ ঘন্টা",
        lessons: [
            { title: "ওয়েবসাইট নিরাপত্তার সেরা প্র্যাকটিস", duration: "১৫:০০" },
            { title: "অ্যাডভান্সড স্পিড অপ্টিমাইজেশন", duration: "২০:০০" },
            { title: "ক্লায়েন্ট হ্যান্ডলিং", duration: "১৫:০০" },
            { title: "Fiverr & Upwork গাইড", duration: "২০:০০" },
            { title: "পোর্টফোলিও তৈরি করা", duration: "১০:০০" },
        ],
    },
];
</script>

<style scoped></style>