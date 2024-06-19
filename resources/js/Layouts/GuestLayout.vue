<script setup>
import { Link } from '@inertiajs/vue3';
</script>

<template>
    <div class="min-h-screen flex flex-col justify-center items-center pt-6 sm:pt-0 bg-gray-100 px-4 sm:px-0">
        <div class="w-full sm:max-w-md mt-6 px-6 py-4 bg-white shadow-md overflow-hidden sm:rounded-lg">
            <div class="text-center mb-4">
                <Link
                    :href="route('home')"
                    class="text-2xl font-bold text-gray-800 hover:text-gray-900"
                >
                    <img src="/images/logo.png" alt="Logo" class="h-20 sm:h-26 mx-auto">
                </Link>
            </div>
            <slot />
        </div>
    </div>
</template>
