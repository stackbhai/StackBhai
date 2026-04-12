<script setup lang="ts">
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";
import { Button } from "~/components/ui/button";
import { Card, CardContent } from "~/components/ui/card";

const freeCourses = [
  {
    title: "HTML বেসিক থেকে অ্যাডভান্স",
    description:
      "ওয়েব ডেভেলপমেন্টের ভিত্তি গড়তে HTML শিখুন একদম শুরু থেকে।\nপ্র্যাকটিক্যাল উদাহরণের মাধ্যমে সহজেই শিখুন।",
    slug: "free-vuejs-tutorial-bangla",
  },
  {
    title: "CSS দিয়ে ডিজাইন মাস্টারি",
    description:
      "ওয়েবসাইটকে আকর্ষণীয় ও রেসপন্সিভ করতে step-by-step এবং modern UI design এর সবকিছু শিখে ফেলুন।",
    slug: "free-laravel-tutorial-bangla",
  },
  {
    title: "WordPress ওয়েবসাইট ডিজাইন",
    description:
      "কোনো কোডিং ছাড়াই সম্পূর্ণ প্রফেশনাল ওয়েবসাইট তৈরি করতে শিখুন। লাইভ প্রজেক্টের মাধ্যমে বাস্তব অভিজ্ঞতা অর্জন করুন।",
    slug: "free-wordpress-web-development-tutorial-bangla",
  },
];

const paidCourses = [
  {
    title: "WordPress ওয়েব ডেভেলপমেন্ট",
    slug: "wordpress-web-development",
    description:
      "লাইভ প্রজেক্টের মাধ্যমে শুরু থেকে সম্পূর্ণ ওয়েবসাইট তৈরি শিখুন step-by-step। মেন্টরশিপ, মার্কেটপ্লেস গাইডলাইন ও ক্লায়েন্ট হ্যান্ডলিং শিখে ইনকাম শুরু করুন।",
    price: 1999,
    oldPrice: 3999,
    batch: "০৩",
    seats: "৩৯",
    startDate: "১৬",
  },
  {
    title: "Vue.js দিয়ে ফ্রন্টএন্ড ডেভেলপমেন্ট",
    description:
      "লাইভ ক্লাসে Vue.js, Nuxt ও modern UI development শিখুন hands-on ভাবে। কোড রিভিউ, প্রজেক্ট ও কমিউনিটি সাপোর্ট সহ complete frontend Mastery।",
    slug: "frontend-web-development-with-vuejs",
    price: 1999,
    oldPrice: 3999,
    batch: "০৩",
    seats: "৩৯",
    startDate: "১৬",
  },
  {
    title: "Full-Stack ওয়েব অ্যাপ ডেভেলপমেন্ট",
    description:
      "৬ মাসে complete roadmap অনুসরণ করে একজন ফুলস্ট্যাক ডেভেলপার হয়ে উঠুন। লাইভ প্রজেক্ট, Laravel + Vue Stack এবং real-world deployment শিখুন।",
    slug: "full-stack-web-app-development",
    price: 1999,
    oldPrice: 3999,
    batch: "০৩",
    seats: "৩৯",
    startDate: "১৬",
  },
];
</script>

<template>
  <section class="py-20 px-6">
    <div class="max-w-6xl mx-auto">
      <!-- TITLE -->
      <h2 class="text-3xl font-bold mb-8 text-center">আমাদের কোর্সসমূহ</h2>

      <!-- TABS -->
      <Tabs
        default-value="free"
        class="w-full flex items-center justify-center"
      >
        <TabsList class="grid grid-cols-2 mb-10 h-full">
          <TabsTrigger value="free" class="p-3 px-8">ফ্রি কোর্স</TabsTrigger>
          <TabsTrigger value="paid" class="p-3 px-8 space-x-1.5">
            <span>লাইভ কোর্স</span>
            <span class="relative flex size-3">
              <span
                class="absolute inline-flex h-full w-full animate-ping rounded-full bg-gray-400 opacity-75"
              ></span>
              <span
                class="relative inline-flex size-3 rounded-full bg-gray-500"
              ></span>
            </span>
          </TabsTrigger>
        </TabsList>

        <!-- FREE COURSES -->
        <TabsContent value="free">
          <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
            <Card v-for="course in freeCourses" :key="course.slug" class="py-3">
              <CardContent class="space-y-1 px-3">
                <NuxtImg
                  src="https://placehold.co/600x400"
                  class="w-full object-cover rounded"
                />
                <h3 class="font-semibold mb-2 flex items-center gap-2">
                  {{ course.title }}

                  <span
                    class="text-xs bg-black text-white px-2 py-1 rounded flex items-center gap-1.5"
                  >
                    <span>ফ্রি</span>
                  </span>
                </h3>
                <p class="text-sm text-gray-600 mb-4 line-clamp-2">
                  {{ course.description }}
                </p>

                <NuxtLink
                  :to="`/courses/${course.slug}`"
                  class="text-sm w-full font-medium hover:underline bg-accent rounded"
                >
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
                <NuxtImg
                  src="https://placehold.co/600x400"
                  class="w-full object-cover rounded"
                />

                <!-- EXTRA INFO -->
                <div
                  class="text-xs text-gray-500 flex flex-row items-center justify-baseline gap-1.5"
                >
                  <!-- BATCH TAG -->
                  <span
                    class="text-xs border px-2 py-1 rounded flex flex-row items-center justify-center gap-1.5"
                  >
                    <Icon name="hugeicons:airdrop" /> ব্যাচ {{ course.batch }}
                  </span>
                  <span
                    class="text-xs border px-2 py-1 rounded flex flex-row items-center justify-center gap-1.5"
                  >
                    <Icon name="hugeicons:user" /> {{ course.seats }} সিট বাকি
                  </span>
                  <span
                    class="text-xs border px-2 py-1 rounded flex flex-row items-center justify-center gap-1.5"
                  >
                    <Icon name="hugeicons:calendar-03" />
                    {{ course.startDate }} দিন বাকি
                  </span>
                </div>
                <!-- TITLE + LIVE BADGE -->
                <h3 class="font-semibold mb-2 flex items-center gap-2">
                  {{ course.title }}

                  <span
                    class="text-xs bg-black text-white px-2 py-1 rounded flex items-center gap-1.5"
                  >
                    <span>লাইভ</span>
                    <span class="relative flex size-2.5">
                      <span
                        class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white/70"
                      ></span>
                      <span
                        class="relative inline-flex size-2 rounded-full bg-white"
                      ></span>
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
                  <NuxtLink
                    :to="`/courses/${course.slug}`"
                    class="text-sm font-medium hover:underline"
                  >
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
