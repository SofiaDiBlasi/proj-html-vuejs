<script>
   import { defineComponent } from 'vue'
   import { Carousel, Navigation, Slide } from 'vue3-carousel'

   import 'vue3-carousel/dist/carousel.css'

   export default  defineComponent ({
      name: "NewArrivals",
      components: {
         Carousel,
         Slide,
         Navigation,
      },
      data: () => ({
         // carousel settings
         settings: {
            itemsToShow: 1,
            snapAlign: 'center',
         },
         // breakpoints are mobile first
         // any settings not specified will fallback to the carousel settings
         breakpoints: {
            // 700px and up
            700: {
               itemsToShow: 3.5,
               snapAlign: 'center',
            },
            // 1024 and up
            1024: {
               itemsToShow: 5,
               snapAlign: 'start',
            },
         },
         bestSellerSlider : [
            "./src/assets/images/spring_printed_dress-400x520.jpg",
            "./src/assets/images/modern_love_tee-400x520.jpg",
            "./src/assets/images/black_leather_jacket-400x520.jpg",
            "./src/assets/images/black_elegant_leather_jacket-400x520.jpg",
            "./src/assets/images/hipster_black_top-400x520.jpg",
            "./src/assets/images/blue_leather_jacket-400x520.jpg",
            "./src/assets/images/black_leather_suit-400x520.jpg",
            "./src/assets/images/blue_jacket_and_white_stripe_tee-400x520.jpg",
            "./src/assets/images/modern_black_leather_suit-400x520.jpg",
            "./src/assets/images/brown_dress_shoes-400x520.jpg"
         ]
      })
   })
</script>

<template>

   <!--contenitore generale-->
   <div class="container-fluid bestSellerBox">
      
      <!--titolo-->
      <div class="row h-30 justify-content-center align-items-center pt-5">
         <div class="col-3"><hr class="mb-5" /></div>
         <div class="col-auto text-center">
            <h1>New Arrivals</h1>
            <p>Brand new products from top designers</p>
         </div>
         <div class="col-3"><hr class="mb-5"/></div>
    </div>  

    <!--slider di img-->
    <!--base template importato-->
    <div class="row justify-content-center align-items-center h-70 pb-5">
         <Carousel v-bind="settings" :breakpoints="breakpoints">
            <Slide v-for="slide in bestSellerSlider" :key="slide">
               <div class="carousel__item">
                  <img class="newArrImg" :src="slide" alt="">
               </div>
            </Slide>
            <template #addons>
               <Navigation />
            </template>
         </Carousel>
    </div>
    
   </div>
</template>

<style class="scss">
   .bestSellerBox{
      height: 720px;
   }
   .carousel__prev, .carousel__next{
      background-color: #c1c1c1;
      color: white;
      height: 70px;
      width: 40px;
   }
   .newArrImg{
      height:  390px;
      width: 300px;
   }
</style>