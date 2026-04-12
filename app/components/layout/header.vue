<script setup lang="ts">
import { ref } from "vue";
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle,
} from "@/components/ui/navigation-menu";
import {
  Sheet,
  SheetClose,
  SheetContent,
  SheetDescription,
  SheetFooter,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet";
import { Button } from "@/components/ui/button";
import {
  ArrowRight,
  Search,
  User,
  Menu,
  Home,
  BookOpen,
  Rss,
  Globe,
  Zap,
  Flame,
  Rocket,
  Monitor,
  Settings,
  X,
} from "lucide-vue-next";
import { Badge } from "../ui/badge";

const showAnnouncement = ref(true);

const freeCourses = [
  {
    title: "HTML বেসিক থেকে অ্যাডভান্স",
    description:
      "ওয়েব ডেভেলপমেন্টের ভিত্তি গড়তে HTML শিখুন একদম শুরু থেকে।\nপ্র্যাকটিক্যাল উদাহরণের মাধ্যমে সহজেই শিখুন।",
    href: "/courses/free-vuejs-tutorial-bangla",
    icon: "hugeicons:html-5",
    badge: null,
  },
  {
    title: "CSS দিয়ে ডিজাইন মাস্টারি",
    description:
      "ওয়েবসাইটকে আকর্ষণীয় ও রেসপন্সিভ করতে step-by-step এবং modern UI design এর সবকিছু শিখে ফেলুন।",
    href: "/courses/free-laravel-tutorial-bangla",
    icon: "hugeicons:css-3",
    badge: null,
  },
  {
    title: "WordPress ওয়েবসাইট ডিজাইন",
    description:
      "কোনো কোডিং ছাড়াই সম্পূর্ণ প্রফেশনাল ওয়েবসাইট তৈরি করতে শিখুন। লাইভ প্রজেক্টের মাধ্যমে বাস্তব অভিজ্ঞতা অর্জন করুন।",
    href: "/courses/free-wordpress-web-development-tutorial-bangla",
    icon: "bi:wordpress",
    badge: "জনপ্রিয়",
  },
];

const liveCourses = [
  {
    title: "WordPress ওয়েব ডেভেলপমেন্ট",
    description:
      "লাইভ প্রজেক্টের মাধ্যমে শুরু থেকে সম্পূর্ণ ওয়েবসাইট তৈরি শিখুন step-by-step। মেন্টরশিপ, মার্কেটপ্লেস গাইডলাইন ও ক্লায়েন্ট হ্যান্ডলিং শিখে ইনকাম শুরু করুন।",
    href: "/courses/wordpress-web-development",
    icon: "cib:wordpress",
    badge: "জনপ্রিয়",
  },
  {
    title: "Vue.js দিয়ে ফ্রন্টএন্ড ডেভেলপমেন্ট",
    description:
      "লাইভ ক্লাসে Vue.js, Nuxt ও modern UI development শিখুন hands-on ভাবে। কোড রিভিউ, প্রজেক্ট ও কমিউনিটি সাপোর্ট সহ complete frontend Mastery।",
    href: "/courses/frontend-web-development-with-vuejs",
    icon: "simple-icons:nuxt",
    badge: null,
  },
  {
    title: "Full-Stack ওয়েব অ্যাপ ডেভেলপমেন্ট",
    description:
      "৬ মাসে complete roadmap অনুসরণ করে একজন ফুলস্ট্যাক ডেভেলপার হয়ে উঠুন। লাইভ প্রজেক্ট, Laravel + Vue Stack এবং real-world deployment শিখুন।",
    href: "/courses/full-stack-web-app-development",
    icon: "mdi:laravel",
    badge: "প্রিমিয়াম",
  },
];

const mobileNavSections = [
  {
    label: "মেনু",
    items: [
      { title: "হোম", href: "/", icon: "hugeicons:home-07" },
      {
        title: "প্রতিষ্ঠাতা সম্পর্কে",
        href: "/about",
        icon: "hugeicons:user-03",
      },
    ],
  },
  {
    label: "ফ্রি কোর্স",
    items: freeCourses,
  },
  {
    label: "লাইভ কোর্স — প্রিমিয়াম",
    items: liveCourses,
  },
];
</script>

<template>
  <!-- Announcement Bar -->
  <Transition name="slide-down">
    <div
      v-if="showAnnouncement"
      class="bg-black text-white text-xs sm:text-sm py-1.5 sm:py-2 px-1 sm:px-4 relative flex items-center justify-between sm:justify-center gap-3"
    >
      <span>
        <strong>গ্র্যান্ড লঞ্চ অফার</strong> — সকল কোর্সে ৪০% ছাড় পাচ্ছেন!
      </span>
      <NuxtLink
        to="/courses"
        class="bg-white text-black rounded px-3 py-0.5 text-xs font-semibold hover:opacity-85 transition-opacity"
      >
        কোর্স গুলো
      </NuxtLink>
      <Button
        size="icon"
        @click="showAnnouncement = false"
        class="absolute right-4 text-white/60 hover:text-white transition-colors"
        aria-label="বন্ধ করুন"
      >
        <X class="w-4 h-4" />
      </Button>
    </div>
  </Transition>

  <!-- Main Header -->
  <header class="sticky top-0 z-50 bg-white border-b h-16 flex items-center">
    <div
      class="container mx-auto w-full flex items-center gap-6 justify-between"
    >
      <!-- Logo -->
      <NuxtLink to="/" class="flex items-center gap-2.5 shrink-0">
        <NuxtImg src="/icon.png" class="w-8 h-8 sm:w-10 sm:h-10" />
      </NuxtLink>

      <!-- Desktop Nav -->
      <div class="hidden md:flex flex-1 items-center justify-center">
        <NavigationMenu>
          <NavigationMenuList>
            <!-- Home -->
            <NavigationMenuItem>
              <NavigationMenuLink
                as-child
                :class="navigationMenuTriggerStyle()"
              >
                <NuxtLink
                  to="/"
                  class="text-[14.5px] font-medium text-gray-500 hover:text-black transition-colors"
                >
                  হোম
                </NuxtLink>
              </NavigationMenuLink>
            </NavigationMenuItem>

            <!-- Free Courses -->
            <NavigationMenuItem>
              <NavigationMenuTrigger
                class="text-[14.5px] font-medium text-gray-500 hover:text-black"
              >
                ফ্রি কোর্স
              </NavigationMenuTrigger>
              <NavigationMenuContent>
                <div class="flex gap-2 p-2 w-lg">
                  <NuxtLink
                    to="/courses"
                    class="w-48 shrink-0 bg-gray-50 rounded-lg p-4 flex flex-col justify-end hover:bg-gray-100 transition-colors"
                  >
                    <span class="text-2xl mb-2">
                      <Icon name="hugeicons:play-circle" />
                    </span>
                    <p
                      class="text-[13.5px] font-semibold text-black leading-snug mb-1"
                    >
                      সকল ফ্রি কোর্স এক্সপ্লোর করুন
                    </p>
                    <p class="text-xs text-gray-400 leading-relaxed">
                      বিনামূল্যে শিখুন, ক্যারিয়ার গড়ুন।
                    </p>
                    <span
                      class="text-xs font-medium text-black mt-3 flex items-center gap-1"
                    >
                      দেখুন <ArrowRight class="w-3 h-3" />
                    </span>
                  </NuxtLink>
                  <div class="flex flex-col gap-0.5 flex-1">
                    <NuxtLink
                      v-for="course in freeCourses"
                      :key="course.href"
                      :to="course.href"
                      class="flex flex-col gap-0.5 px-3 py-2.5 rounded-lg hover:bg-gray-50 transition-colors"
                    >
                      <span
                        class="flex items-center gap-2 text-[13.5px] font-semibold text-black"
                      >
                        <Icon :name="course.icon" />
                        {{ course.title }}
                        <Badge
                          v-if="course.badge"
                          class="bg-black text-white text-[10px] px-1.5 py-0 rounded font-semibold h-auto"
                        >
                          {{ course.badge }}
                        </Badge>
                      </span>
                      <span class="text-xs text-gray-400 leading-snug">{{
                        course.description
                      }}</span>
                    </NuxtLink>
                  </div>
                </div>
              </NavigationMenuContent>
            </NavigationMenuItem>

            <!-- Live Courses -->
            <NavigationMenuItem>
              <NavigationMenuTrigger
                class="text-[14.5px] font-medium text-gray-500 hover:text-black"
              >
                <div class="flex items-center gap-1.5">
                  <span class="relative flex h-2 w-2">
                    <span
                      class="animate-ping absolute inline-flex h-full w-full rounded-full bg-black opacity-30"
                    />
                    <span
                      class="relative inline-flex rounded-full h-2 w-2 bg-black"
                    />
                  </span>
                  লাইভ কোর্স
                </div>
              </NavigationMenuTrigger>
              <NavigationMenuContent>
                <div class="flex gap-2 p-2 w-lg">
                  <NuxtLink
                    to="/courses"
                    class="w-48 shrink-0 bg-gray-50 rounded-lg p-4 flex flex-col justify-end hover:bg-gray-100 transition-colors"
                  >
                    <span class="text-2xl mb-2">
                      <Icon name="hugeicons:live-streaming-01" />
                    </span>
                    <p
                      class="text-[13.5px] font-semibold text-black leading-snug mb-1"
                    >
                      প্রিমিয়াম ক্যারিয়ার ট্র্যাক
                    </p>
                    <p class="text-xs text-gray-400 leading-relaxed">
                      পরিকল্পিত গাইডলাইনে আপনার ক্যারিয়ার গড়ুন।
                    </p>
                    <span
                      class="text-xs font-medium text-black mt-3 flex items-center gap-1"
                    >
                      দেখুন <ArrowRight class="w-3 h-3" />
                    </span>
                  </NuxtLink>
                  <div class="flex flex-col gap-0.5 flex-1">
                    <NuxtLink
                      v-for="course in liveCourses"
                      :key="course.href"
                      :to="course.href"
                      class="flex flex-col gap-0.5 px-3 py-2.5 rounded-lg hover:bg-gray-50 transition-colors"
                      :class="{
                        'border-t border-gray-100 mt-1 pt-3': course.badge,
                      }"
                    >
                      <span
                        class="flex items-center gap-2 text-[13.5px] font-semibold text-black"
                      >
                        {{ course.title }}
                        <Badge
                          v-if="course.badge"
                          class="bg-black text-white text-[10px] px-1.5 py-0 rounded font-semibold h-auto"
                        >
                          {{ course.badge }}
                        </Badge>
                      </span>
                      <span class="text-xs text-gray-400 leading-snug">{{
                        course.description
                      }}</span>
                    </NuxtLink>
                  </div>
                </div>
              </NavigationMenuContent>
            </NavigationMenuItem>

            <div class="h-5 w-px bg-gray-200 mx-1" />

            <NavigationMenuItem>
              <NavigationMenuLink
                as-child
                :class="navigationMenuTriggerStyle()"
              >
                <NuxtLink
                  to="/about"
                  class="text-[14.5px] font-medium text-gray-500 hover:text-black"
                >
                  প্রতিষ্ঠাতা
                </NuxtLink>
              </NavigationMenuLink>
            </NavigationMenuItem>
          </NavigationMenuList>
        </NavigationMenu>
      </div>

      <!-- Search (desktop) 
        <div class="hidden md:flex relative items-center">
          <Search
            class="absolute left-3 text-gray-400 w-3.5 h-3.5 pointer-events-none"
          />
          <Input
            placeholder="কোর্স খুঁজুন..."
            class="pl-9 pr-3 h-9 w-44 focus:w-56 transition-all bg-gray-50 border-transparent focus:border-gray-200 text-sm rounded-lg"
          />
        </div>-->

      <!-- Desktop Actions -->
      <div class="hidden md:flex items-center gap-2">
        <!--
          <NuxtLink to="/auth/login">
            <Button
              variant="outline"
              size="sm"
              class="h-9 gap-1.5 text-[13.5px] font-medium border-gray-200 text-gray-600 hover:text-black hover:bg-gray-50"
            >
              <User class="w-3.5 h-3.5" />
              লগইন
            </Button>
          </NuxtLink>-->
        <NuxtLink to="/courses">
          <Button size="lg" class="">
            শুরু করুন
            <ArrowRight class="w-3.5 h-3.5" />
          </Button>
        </NuxtLink>
      </div>

      <!-- Mobile Menu -->
      <div class="flex md:hidden">
        <Sheet>
          <SheetTrigger as-child>
            <Button
              variant="outline"
              size="icon"
              class="w-9 h-9 border-gray-200"
            >
              <Menu class="w-4 h-4" />
            </Button>
          </SheetTrigger>

          <SheetContent
            side="right"
            class="w-[88%] max-w-sm h-[calc(100dvh-20px)] top-2.5 right-2.5 rounded-2xl border border-gray-100 p-0 flex flex-col"
          >
            <SheetHeader class="px-5 py-4 border-b border-gray-100">
              <SheetTitle class="flex items-center gap-2.5">
                <NuxtImg src="/icon.png" class="w-8 h-8" />
              </SheetTitle>
              <SheetDescription class="sr-only">নেভিগেশন মেনু</SheetDescription>
            </SheetHeader>

            <div class="flex-1 overflow-y-auto px-4">
              <template v-for="(section, si) in mobileNavSections" :key="si">
                <p
                  class="text-[10.5px] font-semibold text-gray-400 uppercase tracking-widest mb-1.5 px-2"
                >
                  {{ section.label }}
                </p>
                <SheetClose
                  as-child
                  v-for="item in section.items"
                  :key="item.href"
                >
                  <NuxtLink
                    :to="item.href"
                    class="flex items-center gap-1.5 px-3 py-2.5 rounded-xl text-xs font-medium text-gray-700 hover:bg-gray-50 hover:text-black transition-colors"
                  >
                    <span
                      class="w-6 h-6 bg-gray-100 rounded-lg flex items-center justify-center flex-shrink-0"
                    >
                      <Icon
                        v-if="item.icon"
                        :name="item.icon"
                        class="w-4 h-4"
                      />
                    </span>
                    <span class="text-xs"> {{ item.title }}</span>
                    <Badge
                      v-if="item.badge"
                      class="ml-auto bg-black text-white text-[10px] px-2 py-0 h-auto font-semibold rounded"
                    >
                      {{ item.badge }}
                    </Badge>
                  </NuxtLink>
                </SheetClose>
              </template>
            </div>

            <SheetFooter
              class="p-4 border-t border-gray-100 flex gap-2 sm:flex-row"
            >
              <SheetClose as-child>
                <NuxtLink to="/auth/login" class="flex-1">
                  <Button
                    variant="outline"
                    class="w-full border-gray-200 text-gray-600 font-medium text-[14px] h-10"
                  >
                    লগইন
                  </Button>
                </NuxtLink>
              </SheetClose>
              <SheetClose as-child>
                <NuxtLink to="/courses" class="flex-1">
                  <Button
                    class="w-full bg-black text-white font-semibold text-[14px] h-10 hover:bg-gray-800"
                  >
                    শুরু করুন →
                  </Button>
                </NuxtLink>
              </SheetClose>
            </SheetFooter>
          </SheetContent>
        </Sheet>
      </div>
    </div>
  </header>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@300;400;500;600;700&display=swap");

.font-siliguri {
  font-family: "Hind Siliguri", sans-serif;
}

.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.25s ease;
}
.slide-down-enter-from,
.slide-down-leave-to {
  transform: translateY(-100%);
  opacity: 0;
}
</style>
