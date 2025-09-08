<script setup lang="ts">
import { ref } from 'vue';
import { Card, CardContent } from "@/components/ui/card";
import TitleSection from '@/components/TitleSection.vue';

const itemsCount = ref<number>(8);

</script>

<template>
    <TitleSection title="Ad Projects"/>
    <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-5 gap-4">
        <Card class="gap-0" v-for="i in itemsCount" :key="i" :class="'p-0 overflow-hidden'">
            <CardContent class="px-0">
                <img :src="'images/ad_' + i + '.jpg'" :alt="'Project ' + i"
                    class="rounded w-full object-cover object-top" />
            </CardContent>
        </Card>
    </div>
</template>