<template>
  <router-link
    :to="{
      name: 'project',
      params: {
        portfolioId: portfolio._id,
        projectId: project._id,
      },
    }"
  >
    <div class="container">
      <h1 class="project-title">{{ project.title }}</h1>
      <div class="image-container">
        <div
          v-for="(image, index) in project.images"
          v-bind:key="index"
          v-prlx="{
            speed: 1.2,
            reverse: true,
            direction: 'x',
            fromBottom: true,
          }"
        >
          <img :src="image" alt />
        </div>
      </div>
    </div>
  </router-link>
</template>

<script>
export default {
  props: ["project", "portfolio"]
};
</script>

<style scoped>
.container {
  width: 100%;
  position: relative;
  margin-bottom: 80px;
}

.project-title {
  z-index: 5;
  position: absolute;
  right: 85px;
  text-align: right;
  font-size: 15rem;
  font-family: "Sail", cursive;
  text-transform: lowercase;
  color: rgba(255, 255, 255, 0.863);

  width: 50%;
  bottom: 10px;
  line-height: 0.5;
}

.image-container {
  display: flex;
  justify-content: flex-end;
  transform: translateX(50%);
  cursor: pointer;
}

img {
  height: 400px;
  margin-right: 50px;
}

@media screen and (max-width: 1200px) {
  .image-container {
    transform: translateX(100%);
  }
}
@media screen and (max-width: 800px) {
  .image-container {
    transform: translateX(200%);
  }
}
@media screen and (max-width: 600px) {
  .image-container {
    transform: translateX(300%);
  }
}
</style>
