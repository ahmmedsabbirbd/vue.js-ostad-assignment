<script setup>
import { ref } from 'vue';

// Sample images (replace with your actual image URLs)
const images = ref([
    'https://via.placeholder.com/800x400?text=Image1',
    'https://via.placeholder.com/800x400?text=Image2',
    'https://via.placeholder.com/800x400?text=Image3',
]);

const currentIndex = ref(0);

const nextSlide = () => {
    if (currentIndex.value < images.value.length - 1) {
        currentIndex.value++;
    }
};

const prevSlide = () => {
    if (currentIndex.value > 0) {
        currentIndex.value--;
    }
};
</script>

<template>
    <div class="carousel-container">
        <div class="carousel">
            <div class="image-wrapper" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
                <div v-for="(image, index) in images" :key="index" class="image-slide">
                    <img :src="image" alt="Image Slide" />
                </div>
            </div>
        </div>

        <div class="carousel-controls">
            <button @click="prevSlide" :disabled="currentIndex === 0">Prev</button>
            <button @click="nextSlide" :disabled="currentIndex === images.length - 1">Next</button>
        </div>
    </div>
</template>

<style scoped>
/* Add your preferred styles here, or use Tailwind CSS classes */

.carousel-container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.carousel {
    overflow: hidden;
    width: 100%;
    position: relative;
}

.image-wrapper {
    display: flex;
    transition: transform 0.3s ease-in-out;
}

.image-slide {
    flex: 0 0 100%;
}

img {
    width: 100%;
    height: auto;
}

.carousel-controls {
    margin-top: 10px;
}

button {
    margin: 0 5px;
}
</style>