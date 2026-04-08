<template>
    <div class="min-h-screen bg-white flex items-center justify-center px-4">

        <div class="w-full max-w-xl bg-white rounded-2xl shadow-md p-6">

            <!-- Title -->
            <h1 class="text-2xl font-semibold text-center mb-2">
                অ্যাকাউন্ট তৈরি করুন
            </h1>
            <p class="text-sm text-gray-500 text-center mb-6">
                নতুন একাউন্ট খুলে শুরু করুন
            </p>

            <!-- Form -->
            <form @submit.prevent="handleRegister" class="space-y-4">

                <!-- Name -->
                <div>
                    <label class="text-sm text-gray-600">নাম</label>
                    <input v-model="name" type="text" placeholder="আপনার নাম লিখুন"
                        class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                </div>

                <div class="flex flex-row gap-2">
                    <!-- Email -->
                    <div>
                        <label class="text-sm text-gray-600">ইমেইল</label>
                        <input v-model="email" type="email" placeholder="আপনার ইমেইল লিখুন"
                            class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                    </div>
                    <!-- Email -->
                    <div>
                        <label class="text-sm text-gray-600">মোবাইল</label>
                        <input v-model="email" type="email" placeholder="আপনার ফোন নম্বর লিখুন"
                            class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                    </div>
                </div>
                <!-- Password -->
                <div>
                    <label class="text-sm text-gray-600">পাসওয়ার্ড</label>
                    <input v-model="password" type="password" placeholder="পাসওয়ার্ড দিন"
                        class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                </div>

                <!-- Confirm Password -->
                <div>
                    <label class="text-sm text-gray-600">পাসওয়ার্ড নিশ্চিত করুন</label>
                    <input v-model="confirmPassword" type="password" placeholder="আবার পাসওয়ার্ড লিখুন"
                        class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                </div>

                <!-- Terms -->
                <label class="flex items-start gap-2 text-sm">
                    <input type="checkbox" v-model="agree" class="mt-1" />
                    আমি শর্তাবলী মেনে নিচ্ছি
                </label>

                <!-- Button -->
                <button type="submit"
                    class="w-full bg-black text-white py-3 rounded-lg font-medium hover:opacity-90 transition">
                    রেজিস্টার করুন
                </button>

            </form>

            <!-- Divider -->
            <div class="my-6 flex items-center gap-2">
                <div class="flex-1 h-px bg-gray-200"></div>
                <span class="text-sm text-gray-400">অথবা</span>
                <div class="flex-1 h-px bg-gray-200"></div>
            </div>

            <!-- Login Link -->
            <p class="text-center text-sm">
                ইতিমধ্যে অ্যাকাউন্ট আছে?
                <NuxtLink to="/auth/login" class="font-medium text-black">
                    লগইন করুন
                </NuxtLink>
            </p>

        </div>

    </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const password = ref('')
const confirmPassword = ref('')
const agree = ref(false)

const handleRegister = () => {
    if (password.value !== confirmPassword.value) {
        alert('পাসওয়ার্ড মিলছে না')
        return
    }

    if (!agree.value) {
        alert('শর্তাবলী মেনে নিতে হবে')
        return
    }

    console.log({
        name: name.value,
        email: email.value,
        password: password.value
    })

    // এখানে Laravel API call দিবা
}
</script>