<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
    </div>
    <p>{{ recipe.descText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious pizza",
              previewText: "Awesome pizza",
              descText: "Some outstanding choices",
              thumbnail:
                "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F19%2F2014%2F07%2F10%2Fpepperoni-pizza-ck-x.jpg&q=60",
            },
            {
              id: "2",
              title: "Delicious burger",
              previewText: "Perfect burger",
              descText: "Some outstanding choices for you",
              thumbnail: "https://media.oneman.gr/onm-images/burger-38.jpg",
            },
          ].find((el) => el.id === context.params.id),
        });
      }, 1500);
    });
  },
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
}
</style>