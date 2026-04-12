<template>
  <div class="min-h-screen">
    <!-- Main Container -->
    <div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-12 gap-6 p-6">
      <!-- Left Side: Video Player + Content -->
      <Card class="lg:col-span-8 space-y-6">
        <CardContent>
          <!-- Video Player -->
          <div class="bg-black rounded-xl overflow-hidden shadow-2xl relative">
            <iframe
              width="815"
              height="458"
              :src="currentLesson.video"
              title="কীভাবে জাপান সাম্রাজ্যের অবিশ্বাস্য উত্থান হয়েছিল | আদ্যোপান্ত | Rise of Japan’s Empire"
              frameborder="0"
              allow="
                accelerometer;
                autoplay;
                clipboard-write;
                encrypted-media;
                gyroscope;
                picture-in-picture;
                web-share;
              "
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>

          <!-- Action Buttons -->
          <div class="flex justify-between p-3 px-0 my-3">
            <Button @click="prevLesson">
              <span> ← আগের লেকচার</span>
            </Button>

            <Button @click="nextLesson"> পরের লেকচার → </Button>
          </div>

          <div class="my-2 pb-2">
            <h2 class="font-semibold text-2xl">
              {{ currentLesson.title }}
            </h2>
            <p class="text-sm">
              {{ currentLesson.description }}
            </p>
          </div>

          <!-- Tabs -->
          <Tabs default-value="desc">
            <TabsList class="bg-transparent space-x-6">
              <TabsTrigger value="desc" class="p-4 px-8">
                ভিডিও ডেসক্রিপশন
              </TabsTrigger>
              <TabsTrigger value="ref" class="p-4 px-8">
                প্রয়োজনীয় রেফারেন্স
              </TabsTrigger>
            </TabsList>
            <TabsContent value="desc">
              <p class="text-xs">{{ currentLesson.description }}</p>
            </TabsContent>
            <TabsContent value="ref">
              <p class="text-xs">{{ currentLesson.note }}</p>
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
              <Input v-model="searchQuery" placeholder="Search lessons..." />
            </div>

            <ScrollArea class="h-[600px]">
              <Accordion
                v-if="filteredModules.length > 0"
                type="single"
                collapsible
                default-value="module-0"
                class="space-y-2"
              >
                <AccordionItem
                  v-for="(module, mIndex) in filteredModules"
                  :key="mIndex"
                  :value="'module-' + mIndex"
                  class="border rounded-lg px-4"
                >
                  <!-- MODULE HEADER -->
                  <AccordionTrigger class="text-left">
                    <div>
                      <p class="font-semibold text-sm">
                        {{ module.title }}
                      </p>
                      <p class="text-xs text-gray-500">
                        {{ module.duration }} • {{ module.total_video }}
                      </p>
                    </div>
                  </AccordionTrigger>

                  <!-- LESSON LIST -->
                  <AccordionContent>
                    <div class="space-y-2 mt-2">
                      <div
                        v-for="(lesson, i) in module.lessons"
                        @click="selectLesson(mIndex, i)"
                        :key="i"
                        class="flex items-center gap-3 px-3 py-2 rounded-lg hover:bg-gray-100 hover:text-black cursor-pointer transition"
                        :class="[
                          'flex items-center gap-3 px-3 py-2 rounded-lg cursor-pointer',
                          currentModuleIndex === mIndex &&
                          currentLessonIndex === i
                            ? 'bg-black text-white'
                            : 'hover:bg-gray-100 hover:text-black',
                        ]"
                      >
                        <!-- NUMBER -->
                        <div
                          class="w-6 h-6 bg-black text-white text-xs flex items-center justify-center rounded"
                        >
                          {{ i + 1 }}
                        </div>
                        <!-- TEXT -->
                        <div class="flex-1">
                          <p class="text-sm line-clamp-2">{{ lesson.title }}</p>
                          <p class="text-xs text-gray-500">
                            {{ lesson.duration }}
                          </p>
                        </div>
                      </div>
                    </div>
                  </AccordionContent>
                </AccordionItem>
              </Accordion>
              <div
                v-else
                class="h-full flex items-center justify-center text-center text-gray-500"
              >
                <div>
                  <p class="text-lg font-semibold flex items-center gap-2">
                    <Icon name="hugeicons:sad-02" />
                    <span>দুঃখিত! কিছুই খুজে পাইনি।</span>
                  </p>
                  <p class="text-sm mt-1">
                    "{{ searchQuery }}" এর জন্য কোনো লেসন পাওয়া যায়নি।
                  </p>
                </div>
              </div>
            </ScrollArea>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Button } from "~/components/ui/button";
import { Card, CardContent } from "~/components/ui/card";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";
import { Input } from "~/components/ui/input";
import { ScrollArea } from "~/components/ui/scroll-area";
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";
const modules = [
  {
    title: "মডিউল ১ - ওয়ার্ডপ্রেস পরিচিতি",
    duration: "১ ঘন্টা ৩০ মিনিট",
    total_video: "৫টি ভিডিও",
    lessons: [
      {
        title: "ওয়ার্ডপ্রেস কী",
        duration: "১০:০০",
        total_video: "৫",
        video: "https://www.youtube.com/embed/Pu3-2rchl9s",
        description:
          "ওয়ার্ডপ্রেস কী এবং এটি কীভাবে কাজ করে তা এই ভিডিওতে আলোচনা করা হয়েছে",
        note: "WordPress হলো একটি জনপ্রিয় CMS",
      },
      {
        title: "WordPress.com vs WordPress.org",
        duration: "০৮:০০",
        video: "https://www.youtube.com/embed/2cbvZf1jIJM",
        description: "দুই প্ল্যাটফর্মের পার্থক্য বুঝানো হয়েছে",
        note: ".org হলো self-hosted version",
      },
      {
        title: "ওয়ার্ডপ্রেস কোথায় ব্যবহার হয়",
        duration: "০৭:০০",
        video: "https://www.youtube.com/embed/3JluqTojuME",
        description: "ব্লগ, বিজনেস ও ই-কমার্সে এর ব্যবহার",
        note: "Flexible platform",
      },
      {
        title: "লোকাল সার্ভারে ইনস্টলেশন",
        duration: "১৫:০০",
        video: "https://www.youtube.com/embed/VCl8z9k8q9s",
        description: "XAMPP ব্যবহার করে ইনস্টলেশন",
        note: "Local development important",
      },
      {
        title: "ড্যাশবোর্ড পরিচিতি",
        duration: "১২:০০",
        video: "https://www.youtube.com/embed/w9FqQ7g3H1M",
        description: "ওয়ার্ডপ্রেস dashboard overview",
        note: "Admin panel understanding",
      },
    ],
  },

  {
    title: "মডিউল ২ - ডোমেইন ও হোস্টিং",
    duration: "১ ঘন্টা ৩০ মিনিট",
    total_video: "৫টি ভিডিও",
    lessons: [
      {
        title: "ডোমেইন কী",
        duration: "১০:০০",
        video: "https://www.youtube.com/embed/e5AwNU3Y2es",
        description: "ডোমেইনের বেসিক ধারণা",
        note: "Domain = website address",
      },
      {
        title: "হোস্টিং কী",
        duration: "১২:০০",
        video: "https://www.youtube.com/embed/NWp4ZpF7N3c",
        description: "হোস্টিং কিভাবে কাজ করে",
        note: "Server concept",
      },
      {
        title: "ডোমেইন কেনা",
        duration: "০৮:০০",
        video: "https://www.youtube.com/embed/4XTsAAHW_Tc",
        description: "কিভাবে domain purchase করতে হয়",
        note: "GoDaddy / Namecheap",
      },
      {
        title: "হোস্টিং কেনা",
        duration: "১০:০০",
        video: "https://www.youtube.com/embed/9gXrK7w6z1Q",
        description: "Hosting provider নির্বাচন",
        note: "Shared vs VPS",
      },
      {
        title: "ডোমেইন + হোস্টিং কানেক্ট",
        duration: "১৫:০০",
        video: "https://www.youtube.com/embed/0d8j8fK7j9w",
        description: "Nameserver setup",
        note: "DNS propagation লাগে",
      },
    ],
  },

  {
    title: "মডিউল ৩ - থিম ও ডিজাইন",
    duration: "১ ঘন্টা ৩০ মিনিট",
    total_video: "৫টি ভিডিও",
    lessons: [
      {
        title: "থিম কী",
        duration: "০৮:০০",
        video: "https://www.youtube.com/embed/Y2b9pXf9d8E",
        description: "থিম কনসেপ্ট ব্যাখ্যা",
        note: "Design control করে",
      },
      {
        title: "ফ্রি থিম ইনস্টল",
        duration: "১২:০০",
        video: "https://www.youtube.com/embed/7wZp9FvX2cA",
        description: "WordPress theme install",
        note: "Appearance > Themes",
      },
      {
        title: "প্রিমিয়াম থিম আপলোড",
        duration: "১০:০০",
        video: "https://www.youtube.com/embed/f9vQ9tK6j3A",
        description: "Premium theme setup",
        note: "Zip upload method",
      },
      {
        title: "থিম কাস্টমাইজ",
        duration: "১৫:০০",
        video: "https://www.youtube.com/embed/5vX9d7gK2hM",
        description: "Customizer ব্যবহার",
        note: "Live preview available",
      },
      {
        title: "রেসপন্সিভ ডিজাইন",
        duration: "১৮:০০",
        video: "https://www.youtube.com/embed/jX5b8F9L2cQ",
        description: "Mobile friendly design",
        note: "Responsive must",
      },
    ],
  },
];
const currentModuleIndex = ref(0);
const currentLessonIndex = ref(0);
const searchQuery = ref("");
const currentLesson = computed(() => {
  return modules[currentModuleIndex.value].lessons[currentLessonIndex.value];
});

const selectLesson = (mIndex, lIndex) => {
  currentModuleIndex.value = mIndex;
  currentLessonIndex.value = lIndex;
};
const nextLesson = () => {
  const module = modules[currentModuleIndex.value];

  if (currentLessonIndex.value < module.lessons.length - 1) {
    currentLessonIndex.value++;
  } else if (currentModuleIndex.value < modules.length - 1) {
    currentModuleIndex.value++;
    currentLessonIndex.value = 0;
  }
};

const prevLesson = () => {
  if (currentLessonIndex.value > 0) {
    currentLessonIndex.value--;
  } else if (currentModuleIndex.value > 0) {
    currentModuleIndex.value--;
    const prevModule = modules[currentModuleIndex.value];
    currentLessonIndex.value = prevModule.lessons.length - 1;
  }
};
const filteredModules = computed(() => {
  if (!searchQuery.value) return modules;

  return modules
    .map((module, mIndex) => {
      const filteredLessons = module.lessons
        .map((lesson, lIndex) => ({
          ...lesson,
          _mIndex: mIndex,
          _lIndex: lIndex,
        }))
        .filter((lesson) =>
          lesson.title.toLowerCase().includes(searchQuery.value.toLowerCase()),
        );

      if (filteredLessons.length > 0) {
        return {
          ...module,
          lessons: filteredLessons,
        };
      }

      return null;
    })
    .filter(Boolean);
});
</script>

<style scoped></style>
