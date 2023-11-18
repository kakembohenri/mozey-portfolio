<script setup>
import background from "../../assets/Images/background/background_pic.jpg"
import DynamicIntro from "../../components/animated_text_cycling.vue"
</script>

<template>
  <!-- :style="{backgroundImage: `url(${background})`}" -->
    <div id="hero" class="hero route bg-image" style="background-color: black;">
    <div class="overlay-itro"></div>
    <div class="hero-content display-table">
      <div class="table-cell">
        <div class="container">
          <h1 class="hero-title mb-4" >Hi there👋, I am 
            <br> Jerry Kwesi Daniels
            </h1>
            <p class="hero-subtitle" style="height:4rem;">
                <!-- <span class="typed" data-typed-items=" Software Developer, Front-end Developer, GIS Developer / Analysis"></span> -->
                <DynamicIntro />
            </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bg-image{
    background-position: top;
}
</style>