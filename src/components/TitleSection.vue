<script setup lang="ts">
import { cn } from '@/lib/utils';

defineProps<{
    title: string
    className?: string
}>();

</script>

<template>
    <div :class="cn(className, 'section-header border-b-2 border-primary mb-8')">
        <h5 class="title text-xl font-semibold text-center text-primary bg-background inline-block translate-y-1/2 px-4"><span>{{ title }}</span></h5>
    </div>
</template>