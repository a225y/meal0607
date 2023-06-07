<template>
  <div class=" bg-white shadow rounded-xl" >
          
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
        <img :src="meal.strMealThumb" 
        class=" rounded-t-xl h-48 w-full object-cover ">
    </router-link>
  
    <div class=" p-3">
        <h2 class=" font-bold ">{{ meal.strMeal }}</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Non magni animi et incidunt, doloremque rem vel 
            obcaecati dignissimos inventore blanditiis eum. 
            Vel eaque itaque obcaecati quisquam ullam corrupti sequi odio?
        </p>
        <div class=" mt-3 mb-3 ">
            <YouTubeButton :href="meal.strYoutube"/>
        </div>    
    </div>
          
  </div> 

</template>  
<script setup>
import YouTubeButton from '../components/YouTubeButton.vue';

const { meal } = defineProps({
  meal: Object
})
</script>
 



