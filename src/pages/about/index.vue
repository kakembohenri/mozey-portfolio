<script setup>
import background from "../../assets/Images/background/background_pic.jpg"
</script>
<template>
    <section id="about" class="about-mf sect-pt4 route ">
      <div class="container">
        <div class="row ">
          <div class="col-sm-12 ">
            <div class="box-shadow-full bg-white text-black">
              <div class="row">
                <div class="col-md-6">
                  <div class="row" style="padding-right: 15px;">
                    <div class="about-img">
                      <img :src="background" class="img-fluid rounded" alt="Profile Pic">
                    </div>
                    <div class="about-info" style="font-size: larger;"> 
                      <p><span class="title-s text-black">Name: </span> <span>Jerry Kwesi Daniels </span></p>
                      <p><span class="title-s text-black">Profile: </span> <span>Front end developer / Software Developer</span></p>
                      <p><span class="title-s text-black">Email: </span> <span>jerrydaniels201@gmail.com</span></p>
                    </div>
                   </div>
                </div>
                <div class="col-md-6">
                  <div class="about-me pt-4 pt-md-0">
                    <div class="title-box-2">
                      <h5 class="title-left text-black">
                        About me
                      </h5>
                    </div>
                    <p class="lead" style="text-align: justify;">
                      I am a self-motivated aspiring developer who is passionate about creating great software products. 
                      I am currently pursuing a master's degree in urban business and development from Malmo University, 
                      as well as a certificate in software development (boot camp). I value teamwork and enjoy contributing 
                      ideas to improve team delivery and customer satisfaction. I also volunteer teaching students 
                      UX/UI design and the fundamentals of front-end development.</p>                  
                  </div>
                  <div class="about-me pt-4 pt-md-0">
                    <div class="title-box-2">
                      <h5 class="title-left text-black">
                        My goal
                      </h5>
                    </div>
                    <p class="lead" style="text-align: justify;">
                      I aim act creating value and contributing to sustainable development using the power of technology. 
                      I also want to be a great software developer capable of constantly improving my skill set 
                      and working in teams to deliver great products and project goals. I take delight in challenges, 
                      learning new things and also supporting my peers through mentorship and training in my areas of strength.                 
                      </p>  
                      <!-- my skills -->
                      <div class="skill-mf">
                        <h3 class="text-black">
                         My skills 
                        </h3>
                        <p style="font-size: larger;">
                         Front-end skills: HTML, CSS, Boostrap, Javascript, UX/UI Design.
                        </p>
                        <p style="font-size: larger;"> GIS Skills: QGIS, ArcGIS, Arcpy</p>
                       </div>  
                    </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section><!-- End About Section -->
</template>