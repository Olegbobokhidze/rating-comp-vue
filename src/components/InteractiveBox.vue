<script setup>
import { defineProps, ref } from "vue";
defineProps({
  header: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  description2: {
    type: String,
    required: true,
  },
  thanks: {
    type: String,
    required: true,
  },
});
const ratingArr = [1, 2, 3, 4, 5, 6];
const selectedRating = ref(null);
const submitted = ref(false);
const handleRatingClick = (rating) => {
  selectedRating.value = rating;
};

const handleSubmit = () => {
  submitted.value = true;
};
</script>

<template>
  <div class="box" v-if="!submitted">
    <h1>{{ header }}</h1>
    <p>{{ description }}</p>
    <div class="ratings">
      <div
        v-for="rating in ratingArr"
        :key="rating"
        class="each-rating"
        @click="handleRatingClick(rating)"
        :class="{
          selected: selectedRating === rating,
        }"
      >
        {{ rating }}
      </div>
    </div>
    <button @click="handleSubmit" :disabled="selectedRating === null">
      Submit
    </button>
  </div>
  <div v-else>
    <div class="box2">
      <h1>Thank You!</h1>
      <p>Your rating <span class="l">{{ selectedRating }}</span>.</p>
      <p>{{ description2 }}</p>
    </div>
  </div>
</template>

<style scoped>
p {
  max-width: 400px;
}

.ratings {
  display: flex;
  flex-direction: row;
  gap: 20px;
}
.each-rating {
  background-color: blue;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.each-rating:hover {
  background-color: whitesmoke;
  color: black;
}
button {
  height: 50px;
  width: 200px;
  background-color: grey;
  font-size: 20px;
  color: wheat;
  border-radius: 15px;
  outline: none;
  border: none;
  cursor: pointer;
}
button:hover {
  background-color: whitesmoke;
  color: black;
}
.selected {
  background-color: whitesmoke;
  color: black;
}
.l{
   font-weight: bold;
}
.box2 {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    flex-direction: column;
}
</style>
