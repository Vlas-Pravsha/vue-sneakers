<script setup>
defineProps({
    id: Number,
    title: String,
    imageUrl: String,
    price: Number,
    isFavorite: Boolean,
    isAdded: Boolean,
    onClickFavorite: Function,
    onClickAdd: Function
})
</script>

<template>
    <div
        class="relative bg-white border border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl">
        <img v-if="onClickFavorite" :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'" alt="Like 1"
            class="absolute top-8 left-8 w-12 h-12" @click="onClickFavorite" />

        <img :src="imageUrl" alt="Sneaker" class="w-80 h-60 " />

        <p class="mt-2">{{ title }}</p>

        <div class="flex justify-between mt-5">
            <div class="flex flex-col">
                <span class="text-slate-400">Цена:</span>
                <b>{{ price }} ua.</b>
            </div>

            <img v-if="onClickAdd" @click="onClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="Plus"
                class="w-10 h-10" />
        </div>
    </div>
</template>