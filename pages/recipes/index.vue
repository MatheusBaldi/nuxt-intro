<template>
  <section class="recipes">
    <Recipe 
      :key="index" 
      v-for="(recipe, index) in recipes"
      :thumbnail="recipe.thumbnail" 
      :title="recipe.title" 
      :id="recipe.id"
      :previewText="recipe.previewText"/>
  </section>    
</template>

<script>
import Recipe from '@/components/Recipe';

export default {
  components: {
    Recipe
  },
  asyncData(){
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: '1',
              title: 'Delicios food',
              previewText: "This is a food",
              thumbnail:"https://www.marinabaysands.com/content/dam/singapore/marinabaysands/master/main/home/restaurants/foodie%20guide/Nasi%20lemak_500x340.jpg" 
            },
            {
              id: '2',
              title: 'Some other food',
              previewText: "This is another food",
              thumbnail:"https://www.thelocal.it/userdata/images/article/69523836b0191608c41d640feead8da2be5462038d3409e1e3900fad039c7fc8.jpg"
            },
          ]
        })
      })
    });
  }
}
</script>

<style scoped>
.recipes{
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
