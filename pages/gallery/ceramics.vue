<template>
  <div id="page" class="photos">
    <div v-for="(image, index) in images" :key="index">
      <div class="card">
        <button @click="showModal(index)">
          <img :src="image.path" :alt="image.alt" />
        </button>
        <!-- <p>{{ image.description }}</p> -->
      </div>
    </div>
  </div>

  <!-- TODO: move image slider into components later -->
  <!-- modal -->
  <div class="modal-slider-wrapper" v-show="modalActive">
    <div class="modal-slider">
      <button class="slider-control right close" @click="closeModal">
        <Icon name="ep:close" size="30px" />
      </button>
      <button class="slider-control left" @click="showPrevious">
        <Icon name="ep:arrow-left" size="30px" />
      </button>
      <button class="slider-control right" @click="showNext">
        <Icon name="ep:arrow-right" size="30px" />
      </button>
      <div class="modal-slider-item" 
        v-for="(image, index) in images" 
        v-show="currentSlide === index"
        :image="image"
        :key="index" 
        :currentSlide="currentSlide" 
        :index="index">
        <img :src="image.path" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: 0,
      modalActive: false,
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
  methods: {
    showModal(i) {
      this.currentSlide = i;
      console.log(`This.currentSlide: ${this.currentSlide}`);
      if (this.modalActive === false) {
        this.modalActive = true
      }
    },
    closeModal() {
      if (this.modalActive === true) {
        this.modalActive = false
      }
    },
    setCurrentSlide(index) {
      this.currentSlide = index;
    },
    showPrevious() {
      const index = this.currentSlide > 0 ? this.currentSlide - 1 : this.images.length - 1;
      this.setCurrentSlide(index);
    },
    showNext() {
      const index = this.currentSlide < this.images.length - 1 ? this.currentSlide + 1 : 0;
      this.setCurrentSlide(index);
    },
  },
};
</script>

<style scoped>
.modal-slider-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.modal-slider {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-left: 10%;
  padding-right: 10%;
  background-color: black;
}

.modal-slider-item {
  height: calc(100vh);
}

.modal-slider-item img {
  max-width: 100%; 
  height: 100%;
}

.slider-control {
  position: absolute;
  top: calc(50%);
  color: white;
  cursor: pointer;
  width: 50px;
  height: 50px;
  transition: opacity .2s;
}

.close {
  top: 0;
}

.left {
  left: 0;
}

.right {
  right: 0;
}
</style>
