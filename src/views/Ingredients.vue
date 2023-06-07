<template>
    <div class=" p-8">
       
        <div class="mb-4 text-4xl font-bold">相關食譜：</div>
        <router-link 
        :to="{name:'byIngredient',
        params: { ingredient: item.strIngredient }}"
        v-for="item in ingredients" :key="item.strIngredient"

        class=" block mb-3 p-4 bg-red-300 rounded shadow">
            <h1 class=" text-2xl font-bold">{{ item.strIngredient }}</h1>
            <p> {{ item.strDescription }}</p>
        </router-link>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router';
import axiosClient from '../axiosClient';
import YouTubeButton from '../components/YouTubeButton.vue';


const route = useRoute();
const ingredients = ref([]);

onMounted(() => {
    axiosClient.get("list.php?i=list")
        .then(({ data }) => {
            ingredients.value = data.meals
        })
})


</script>
