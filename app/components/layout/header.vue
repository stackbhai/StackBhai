<script setup lang="ts">
import { CircleCheckIcon, CircleHelpIcon, CircleIcon } from 'lucide-vue-next'
import {
    NavigationMenu,
    NavigationMenuContent,
    NavigationMenuItem,
    NavigationMenuLink,
    NavigationMenuList,
    NavigationMenuTrigger,
    navigationMenuTriggerStyle,
} from '@/components/ui/navigation-menu'
import Button from '../ui/button/Button.vue';
</script>

<template>
    <div class="flex h-16 sticky top-0 z-50 bg-white items-center justify-between px-4">
        <div class="flex items-center space-x-2">
            <Button variant="default" size="icon">
                <Icon name="hugeicons:anonymous" class="text-lg" />
            </Button>
            <h1 class="text-2xl font-bold">Stack Bhai</h1>
        </div>
        <div>
            <NavigationMenu>
                <NavigationMenuList>
                    <NavigationMenuItem>
                        <NavigationMenuLink as-child :class="navigationMenuTriggerStyle()">
                            <NuxtLink to="/">হোম</NuxtLink>
                        </NavigationMenuLink>
                    </NavigationMenuItem>
                    <NavigationMenuItem>
                        <NavigationMenuTrigger>সকল কোর্স</NavigationMenuTrigger>
                        <NavigationMenuContent>
                            <ul class="grid gap-2 md:w-[450px] lg:w-[500px] lg:grid-cols-[.75fr_1fr]">
                                <li class="row-span-3">
                                    <NavigationMenuLink as-child>
                                        <NuxtLink
                                            class="from-muted/50 to-muted flex h-full w-full flex-col justify-end rounded-md bg-linear-to-b p-4 no-underline outline-hidden select-none focus:shadow-md"
                                            to="/courses">
                                            <div class="mt-4 text-lg font-medium flex items-center gap-2">
                                                ফ্রি কোর্সগুলো দেখুন
                                                <Icon name="hugeicons:arrow-up-right-02" class="text-xl" />
                                            </div>
                                            <p class="text-muted-foreground text-xs leading-tight">
                                                আমাদের সকল ফ্রি কোর্স গুলো এক্সপ্লোর করুন। এবং প্রিমিয়াম সাপোর্টের জন্য
                                                আমাদের পেইড কোর্স দেখুন।
                                            </p>
                                        </NuxtLink>
                                    </NavigationMenuLink>
                                </li>
                                <NuxtLink to="/courses/free-wordpress-web-development-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">WordPress Web Development</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ওয়ার্ডপ্রেস দিয়ে আধুনিক ও রেসপন্সিভ ওয়েবসাইট তৈরি শিখুন সম্পূর্ণ ফ্রিতে।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/free-vuejs-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">Vue.js Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ফ্রন্টএন্ডে Vue.js দিয়ে ডাইনামিক ও দ্রুতগতির ওয়েব অ্যাপ তৈরি করতে শিখুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/free-laravel-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">Laravel Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ব্যাকএন্ডের জন্য Laravel ব্যবহার করে শক্তিশালী ও স্কেলেবল ওয়েব অ্যাপ তৈরি
                                            করুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/free-laravel-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">HTML জিরো থেকে হিরো

                                        </h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ব্যাকএন্ডের জন্য Laravel ব্যবহার করে শক্তিশালী ও স্কেলেবল ওয়েব অ্যাপ তৈরি
                                            করুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/free-laravel-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">Laravel Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ব্যাকএন্ডের জন্য Laravel ব্যবহার করে শক্তিশালী ও স্কেলেবল ওয়েব অ্যাপ তৈরি
                                            করুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/free-laravel-tutorial-bangla">
                                    <NavigationMenuLink>
                                        <h1 class="text-sm font-medium">Laravel Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ব্যাকএন্ডের জন্য Laravel ব্যবহার করে শক্তিশালী ও স্কেলেবল ওয়েব অ্যাপ তৈরি
                                            করুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                            </ul>
                        </NavigationMenuContent>
                    </NavigationMenuItem>
                    <NavigationMenuItem>
                        <NavigationMenuTrigger>
                            <div class="flex flex-row gap-1.5 items-center justify-center">
                                <span class="relative flex size-3">
                                    <span
                                        class="absolute inline-flex h-full w-full animate-ping rounded-full bg-gray-400 opacity-75"></span>
                                    <span class="relative inline-flex size-3 rounded-full bg-gray-500"></span>
                                </span>
                                <span>লাইভ কোর্স</span>
                            </div>
                        </NavigationMenuTrigger>
                        <NavigationMenuContent>
                            <ul class="grid gap-2 md:w-[450px] lg:w-[500px] lg:grid-cols-[.75fr_1fr]">
                                <li class="row-span-4">
                                    <NavigationMenuLink as-child>
                                        <NuxtLink
                                            class="from-muted/50 to-muted flex h-full w-full flex-col justify-end rounded-md bg-linear-to-b p-4 no-underline outline-hidden select-none focus:shadow-md"
                                            to="/courses">
                                            <div class="mt-4 text-lg font-medium flex items-center gap-2">
                                                প্রিমিয়াম কোর্সগুলো
                                                <Icon name="hugeicons:arrow-up-right-02" class="text-xl" />
                                            </div>
                                            <p class="text-muted-foreground text-xs leading-tight">
                                                পরিকল্পিত ও
                                                পরিক্ষিত গাইড লাইনের মাধ্যমে আপনার ক্যারিয়ার গড়তে আমরা থাকবো আপনার সাথে।
                                            </p>
                                        </NuxtLink>
                                    </NavigationMenuLink>
                                </li>
                                <NuxtLink to="/courses/wordpress-web-development">
                                    <NavigationMenuLink to="/courses/wordpress-web-development">
                                        <h1 class="text-sm font-medium">WordPress Web Development</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ওয়ার্ডপ্রেস দিয়ে আধুনিক ও রেসপন্সিভ ওয়েবসাইট তৈরি শিখুন সম্পূর্ণ ফ্রিতে।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/wordpress-web-development">
                                    <NavigationMenuLink to="/courses/frontend-web-development-with-vuejs">
                                        <h1 class="text-sm font-medium">Vue.js Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ফ্রন্টএন্ডে Vue.js দিয়ে ডাইনামিক ও দ্রুতগতির ওয়েব অ্যাপ তৈরি করতে শিখুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/wordpress-web-development">
                                    <NavigationMenuLink to="/courses/backend-development-with-laravel">
                                        <h1 class="text-sm font-medium">Laravel Mastery</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            ব্যাকএন্ডের জন্য Laravel ব্যবহার করে শক্তিশালী ও স্কেলেবল ওয়েব অ্যাপ তৈরি
                                            করুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                                <NuxtLink to="/courses/wordpress-web-development">
                                    <NavigationMenuLink to="/courses/full-stack-web-app-development">
                                        <h1 class="text-sm font-medium">Full-Stack Development</h1>
                                        <p class="text-muted-foreground text-xs leading-tight">
                                            Full-Stack ডেভেলপার হিসেবে নিজের ক্যারিয়ার গড়তে, ৬ মাসের চ্যালেঞ্জ নিন। AI
                                            যুগে
                                            নিজেকে এগিয়ে রাখুন।
                                        </p>
                                    </NavigationMenuLink>
                                </NuxtLink>
                            </ul>
                        </NavigationMenuContent>
                    </NavigationMenuItem>
                    <NavigationMenuItem>
                        <NavigationMenuLink as-child>
                            <NuxtLink to="/">প্রতিষ্ঠাতা সম্পর্কে</NuxtLink>
                        </NavigationMenuLink>
                    </NavigationMenuItem>
                </NavigationMenuList>
            </NavigationMenu>
        </div>
        <div class="flex items-center space-x-4">
            <NuxtLink to="/auth/login">
                <Button variant="outline" size="lg">
                    <Icon name="hugeicons:user-03" class="text-base" />
                    <span>লগইন</span>
                </Button>
            </NuxtLink>
            <Button variant="default" size="icon">
                <Icon name="hugeicons:whatsapp" class="text-xl" />
            </Button>
        </div>
    </div>
</template>
