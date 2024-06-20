<script setup>
import { Link } from '@inertiajs/vue3';

const props = defineProps({
    href: {
        type: String,
        required: true,
    }
});
</script>

<template>
    <Link :href="href" class="inline-flex items-center justify-center px-1 pt-1 text-base font-medium leading-5 text-gray-900 focus:outline-none transition duration-150 ease-in-out">
        <slot />
    </Link>
</template>