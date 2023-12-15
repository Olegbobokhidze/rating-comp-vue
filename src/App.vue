<script setup>
import InteractiveBox from "./components/InteractiveBox.vue";
const description2 =
  "We appreciate you taking the time to give a rating. If you ever need more support, don't hesitate to get in touch!";
const description =
  "Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!";
</script>

<template>
  <div class="box">
    <InteractiveBox
      thanks="Thank You"
      header="How did we do?"
      :description="description"
      :description2="description2"
    />
  </div>
</template>

<style scoped>
.box {
  align-self: center;
  display: flex;
  align-items: left;
  flex-direction: column;
  min-width: 600px;
  height: 500px;
  background-color: #1f262f;
  border-radius: 30px;
  padding: 40px;
  gap: 20px;
}
</style>
