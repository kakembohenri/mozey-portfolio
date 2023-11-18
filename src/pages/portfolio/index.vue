<script setup>
    // import personal_web from "../../assets/Images/background/background.jpg"
    import agri_business from "../../assets/Images/background/first_website.jpg"
    import construction from "../../assets/Images/background/Mic_construction_company1.jpg"
    import recipe from "../../assets/Images/background/Recipe_website.jpg"
    // gis
    import car_crimes from "../../assets/portfolio/gis/car crimes in Malmo.jpg"
    import heat_map from "../../assets/portfolio/gis/Heatmap of Malmo.jpg"
    import income_map from "../../assets/portfolio/gis/Gross income map.jpg"
</script>
<template>
    <section id="work" class="portfolio-mf sect-pt4 route">
      <div class="container">
        <div class="row">
          <div class="col-sm-12">
            <div class="title-box text-center">
              <h3 class="title-a">
                Portfolio
              </h3>
              <p class="subtitle-a">
                Check out my recent work
              </p>
              <div class="line-mf"></div>
            </div>
          </div>
        </div>
        <div class="row">
            <div class="col-md-4 ">
                <div class="portfolio1">
                <img :src="car_crimes" alt="Car crimes" />
                <p>
                    Map of Car crimes in Malmo 
                    </p>
                </div>
            </div>
            <div class="col-md-4 ">
                <div class="portfolio1">
                <img :src="heat_map" alt="Heat map" />
                <p>
                    Heat map of house transactions 
                    </p>
                </div>
            </div>
            <div class="col-md-4 ">
                <div class="portfolio1">
                <img :src="income_map" alt="Gross Income map" />
                <p>
                    Gross income levels in Malmo 
                    </p>
                </div>
            </div>
            <div class="col-md-4">
                <div class="portfolio1">
                <img :src="agri_business" alt="green agribusiness" />
                <p>
                    Green Agribusiness 
                </p>    
                </div>
            </div>
            <div class="col-md-4">
                <div class="portfolio1">
                <img :src="construction" alt="mic construction" />
                <p>
                    Mic construction company website 
                </p>
                </div>
            </div>
            <div class="col-md-4">
                <div class="portfolio1">
                <img :src="recipe" alt="Recipe restaurant" />
                <p>
                    Simply Recipe Restaurant 
                </p>
        
                </div>
            </div>
          </div>
        </div>
        <!-- <div class="rowdivision">
          <div class="rowdivision1" style="visibility: hidden;">
          </div>
          <div class="rowdivision2 more-container">            
              <span> Show more </span>
          </div>
          <div class="rowdivision3" style="visibility: hidden;">
          </div>      
        </div> -->
    </section>
</template>

<style scoped>
  .more-container{
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }

  .more-container > span{
    color: #fff;
  }
</style>