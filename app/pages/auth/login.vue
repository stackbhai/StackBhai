<template>
    <div class="min-h-screen bg-white flex items-center justify-center px-4">

        <div class="w-full max-w-md bg-white rounded-2xl shadow-md p-6">

            <!-- Title -->
            <h1 class="text-2xl font-semibold text-center mb-2">
                লগইন করুন
            </h1>
            <p class="text-sm text-gray-500 text-center mb-6">
                আপনার অ্যাকাউন্টে প্রবেশ করুন
            </p>

            <!-- Form -->
            <form @submit.prevent="handleLogin" class="space-y-4">

                <!-- Email -->
                <div>
                    <label class="text-sm text-gray-600">ইমেইল</label>
                    <input v-model="email" type="email" placeholder="আপনার ইমেইল লিখুন"
                        class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                </div>

                <!-- Password -->
                <div>
                    <label class="text-sm text-gray-600">পাসওয়ার্ড</label>
                    <input v-model="password" type="password" placeholder="আপনার পাসওয়ার্ড লিখুন"
                        class="w-full mt-1 px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-black" />
                </div>

                <!-- Remember + Forgot -->
                <div class="flex items-center justify-between text-sm">
                    <label class="flex items-center gap-2">
                        <input type="checkbox" v-model="remember" />
                        মনে রাখুন
                    </label>
                    <a href="#" class="text-black font-medium">
                        পাসওয়ার্ড ভুলে গেছেন?
                    </a>
                </div>

                <!-- Button -->
                <button type="submit"
                    class="w-full bg-black text-white py-3 rounded-lg font-medium hover:opacity-90 transition">
                    লগইন
                </button>

            </form>

            <!-- Divider -->
            <div class="my-6 flex items-center gap-2">
                <div class="flex-1 h-px bg-gray-200"></div>
                <span class="text-sm text-gray-400">অথবা</span>
                <div class="flex-1 h-px bg-gray-200"></div>
            </div>

            <!-- Register -->
            <p class="text-center text-sm">
                নতুন অ্যাকাউন্ট?
                <NuxtLink to="/auth/register" class="font-medium text-black">
                    রেজিস্টার করুন
                </NuxtLink>
            </p>

        </div>

    </div>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const remember = ref(false)

const handleLogin = () => {
    console.log({
        email: email.value,
        password: password.value,
        remember: remember.value
    })

    // এখানে API call দিবা (Laravel API)
}
</script>