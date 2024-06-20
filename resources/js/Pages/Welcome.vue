<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    }
});
</script>

<template>
    <Head title="Добро пожаловать" />

    <div class="relative flex items-center justify-center min-h-screen bg-center bg-gray-100 selection:bg-red-500 selection:text-white px-4 sm:px-0">
        <!-- Main Content Section -->
        <div class="bg-white p-6 sm:p-8 rounded-lg shadow-lg text-center max-w-md w-full">
            <!-- Logo -->
            <div class="mb-4">
                <img src="/images/logo.png" alt="Logo" class="h-20 sm:h-26 mx-auto">
            </div>

            <!-- Description -->
            <h1 class="text-xl sm:text-2xl font-bold text-gray-800 mb-2">Добро пожаловать в нашу социальную сеть</h1>
            <p class="text-gray-600 mb-6">Объединяя людей, создавая сообщества.</p>

            <!-- Buttons -->
            <div v-if="canLogin">
                <Link
                    v-if="$page.props.auth.user"
                    :href="route('home')"
                    class="inline-block w-full py-2 px-4 mb-2 bg-blue-500 text-white font-semibold rounded-lg hover:bg-blue-700"
                >Главная</Link>

                <template v-else>
                    <Link
                        :href="route('login')"
                        class="inline-block w-full py-2 px-4 mb-2 bg-gray-800 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest hover:bg-gray-700 focus:bg-gray-700 active:bg-gray-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150"
                    >Войти</Link>

                    <Link
                        v-if="canRegister"
                        :href="route('register')"
                        class="inline-block w-full py-2 px-4 mb-2 bg-gray-800 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest hover:bg-gray-700 focus:bg-gray-700 active:bg-gray-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150"
                    >Регистрация</Link>
                </template>
            </div>
        </div>
    </div>
</template>

<style>
</style>
