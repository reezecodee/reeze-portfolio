<template>
    <div class="grid grid-cols-[repeat(auto-fit,minmax(64px,1fr))] gap-3 mb-7">
        <div v-for="crypto in api.cryptos" :key="`crypto-${crypto.id}`"
            class="group p-3 cursor-pointer w-full max-w-[80px] mx-auto">
            <img :src="`https://dknfcfcucbesgjhduhnv.supabase.co/storage/v1/object/public/cryptos
/${crypto.icon}`" class="w-14 rounded mb-1" :class="{ 'dark:invert': crypto.dark_invert }">
            <p class="text-center text-xs">{{ crypto.percent }}%</p>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useApiStore } from '@/stores/useApiStore.js';

const api = useApiStore()
</script>