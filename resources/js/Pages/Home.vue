<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";
</script>

<template>
  <Head title="Главная" />

  <AuthenticatedLayout>
    <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
      <div
        class="p-6 text-gray-900 border border-gray-300 rounded-lg shadow-lg"
      >
        <h2 class="text-2xl font-bold mb-4">
          Добро пожаловать на нашу платформу!
        </h2>
        <p class="mb-4">
          Вы успешно авторизованы! Теперь у вас есть доступ ко всем функциям
          нашего сайта. Здесь вы можете создавать и управлять своими постами,
          просматривать профили других пользователей, а также участвовать в
          обсуждениях.
        </p>
        <p class="mb-4">
          Если у вас возникнут вопросы, вы всегда можете обратиться в нашу
          службу поддержки. Мы стремимся сделать ваш опыт использования нашего
          сайта максимально комфортным и приятным.
        </p>
        <p class="mb-4">
          Не забудьте заполнить свой профиль и начать взаимодействие с другими
          участниками сообщества. Чем активнее вы будете, тем больше
          возможностей откроется перед вами!
        </p>
        <p class="mb-4">
          Спасибо, что выбрали нашу платформу. Мы надеемся, что вам здесь
          понравится.
        </p>
      </div>
    </div>
  </AuthenticatedLayout>
</template>
