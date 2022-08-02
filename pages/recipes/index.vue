<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :id="recipe.id"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :thumbnail="recipe.thumbnail"
    />
  </section>
</template>

<script>
import Recipe from "../../components/Recipe.vue";
export default {
  components: {
    Recipe,
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Delicious pizza",
              previewText: "Awesome pizza",
              thumbnail:
                "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F19%2F2014%2F07%2F10%2Fpepperoni-pizza-ck-x.jpg&q=60",
            },
            {
              id: "2",
              title: "Delicious burger",
              previewText: "Perfect burger",
              thumbnail: "https://media.oneman.gr/onm-images/burger-38.jpg",
            },
          ],
        });
      }, 1500);
    });
  },
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
.recipe {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
}
.thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>>
