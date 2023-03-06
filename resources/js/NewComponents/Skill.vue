<script setup>
    defineProps({
        background: String,
});
</script>

<template>
    <section class="flex items-center px-44 py-6 justify-between">
        <div :class="background" class="h-24, w-24 rounded-full boreder-double border-8">
            <p class="text-2xl font-extrabold text-gray-800 mx-1">
                <slot></slot>
            </p>
        </div>
    </section>
</template>
