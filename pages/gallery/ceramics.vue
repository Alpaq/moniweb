<template>
  <div id="page" class="photos">
    <div v-for="(image, index) in images" :key="index">
      <div class="card">
        <button>
          <img :src="image.path" :alt="image.alt" />
        </button>
        <!-- <p>{{ image.description }}</p> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { id: "1", path: "/img/ceramics/1.jpg", alt: "Image 1", description: "Description" },
        { id: "2", path: "/img/ceramics/2.jpg", alt: "Image 2", description: "Description" },
        { id: "3", path: "/img/ceramics/3.jpg", alt: "Image 3", description: "Description" },
        { id: "4", path: "/img/ceramics/4.jpg", alt: "Image 4", description: "Description" },
        { id: "5", path: "/img/ceramics/5.jpg", alt: "Image 5", description: "Description" },
        { id: "6", path: "/img/ceramics/6.jpg", alt: "Image 6", description: "Description" },
        { id: "7", path: "/img/ceramics/7.jpg", alt: "Image 7", description: "Description" },
        { id: "8", path: "/img/ceramics/8.jpg", alt: "Image 8", description: "Description" },
        { id: "9", path: "/img/ceramics/9.jpg", alt: "Image 9", description: "Description" },
        { id: "10", path: "/img/ceramics/10.jpg", alt: "Image 10", description: "Description" },
        { id: "11", path: "/img/ceramics/11.jpg", alt: "Image 11", description: "Description" },
        { id: "12", path: "/img/ceramics/12.jpg", alt: "Image 12", description: "Description" },
      ]
    };
  },
};
</script>
