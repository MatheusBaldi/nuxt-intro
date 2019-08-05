<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.description }}</p>
  </section>
</template>

<script>

export default {
  asyncData(context){
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: '1',
              title: 'Delicios food',
              previewText: "This is a food",
              description: "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
              thumbnail:"https://www.marinabaysands.com/content/dam/singapore/marinabaysands/master/main/home/restaurants/foodie%20guide/Nasi%20lemak_500x340.jpg" 
            },
            {
              id: '2',
              title: 'Some other food',
              previewText: "This is another food",
              description: "bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb",
              thumbnail:"https://www.thelocal.it/userdata/images/article/69523836b0191608c41d640feead8da2be5462038d3409e1e3900fad039c7fc8.jpg"
            },
          ].find((recipe) => recipe.id === context.params.id)
        })
      }, 1500)
    });
  }
}
</script>

<style scoped>
.single-recipe{
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image{
  width: 100%;
}
</style>
