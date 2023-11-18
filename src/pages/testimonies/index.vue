<script setup>
    // import overlay from "../../assets/img/overlay-bg.jpg"
    // import "../../assets/vendor/swiper/swiper-bundle.min.js"
    import {ref} from 'vue'

    let number = ref(1)

    const handlePick = (pick) => {
      number.value = pick
    }

    // translateX(-100%)
    // translateX(-100%)
</script>

<template>
    <!-- style="background-image: url(assets/img/overlay-bg.jpg)" -->
    <div class="testimonials paralax-mf bg-image" >
      <!-- <div class="overlay-mf"></div> -->
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="testimonials-slider swiper" data-aos="fade-up" data-aos-delay="100">
              <div class="swiper-wrapper">
                <div class="swiper-slide bg-white card">
                  <div class="testimonial-box">
                    <div class="author-test">
                      <!-- <img src="Images/personalimages/ratings/wandie1.jpg" alt="" class="rounded-circle b-shadow-a" width="150px" height="150px"> -->
                      <span class="author text-black"> Wanereeba Innocent</span>
                    </div>

                    <div class="content-test ">
                      <h3 class="text-black"> Full stack developer</h3>
                      <p class="description lead text-black">
                        Jerry Daniels is an ambitious and excellent software developer. 
                        I have worked with him on quite a number of projects to help 
                        businesses grow by building their websites and softwares to enhance their productivity.
                      </p>
                    </div>
                    
                  </div>
                </div><!-- End testimonial item -->
                <div class="swiper-slide bg-white card" :style="{transform: number === 2 ? 'translateX(-100%)':'translateX(0)'}">
                  <div class="testimonial-box">
                    <div class="author-test">
                      <!-- <img src="Images/personalimages/ratings/Eric.jpeg" alt="" class="rounded-circle b-shadow-a" width="150px" height="150px"> -->
                      <span class="author text-black"> Okello Efprem </span>
                    </div>
                    <div class="content-test">
                      <h3 class="text-black"> Front-end developer </h3>
                      <p class="description lead text-black">
                        Jerry Daniels is an inspiration to many. Personally I have known him since 2014 from 
                        Makerere University when we were exploring how to utilise the power of technology to contribute to 
                        sustainable development. He is passionate and committed to accomplishing whatever task that comes to him. 
                        I have benefitted from his self-taught craft.
                      </p>
                    </div>
                  </div>
                </div><!-- End testimonial item -->
              </div>
              <!-- <div class="swiper-pagination"></div> -->
              <div class="swiper-pagination swiper-pagination-clickable swiper-pagination-bullets swiper-pagination-horizontal">
                <span :class="{'swiper-pagination-bullet': number !== 1, 'swiper-pagination-bullet swiper-pagination-bullet-active': number===1}" tabindex="0" role="button" aria-label="Go to slide 1" aria-current="true" @click="handlePick(1)"></span>
                <span :class="{'swiper-pagination-bullet': number !== 2, 'swiper-pagination-bullet swiper-pagination-bullet-active': number===2}" tabindex="0" role="button" aria-label="Go to slide 2" @click="handlePick(2)"></span></div>
            </div>          
        </div> 
          </div>
        </div>
      </div>
</template>