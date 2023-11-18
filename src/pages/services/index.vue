<script setup>
import webdev from "../../assets/Images/services/developer.png"
import ui from "../../assets/Images/services/computer.png"
import gis from "../../assets/Images/services/gis.jpg"

</script>
<template>
    <section id="services" class="services-mf pt-5 route">
      <div class="container">
        <div class="row">
          <div class="col-sm-12">
            <div class="title-box text-center">
              <h3 class="title-a">
                Services
              </h3>
              <p class="subtitle-a" style="font-size: large;">
                Here are the things that I offer in my line of work
              </p>
              <div class="line-mf"></div>
            </div>
          </div>
        </div>
        <div class="row">
            <div class="col-md-4">
            <div class="service-box">
              <div class="service-ico">
                <span>
                    <img :src="webdev" alt="web dev" style="width:70px;, height:70px;" />
                </span>
              </div>
              <div class="service-content">
                <h2 class="s-title"> Web Development</h2>
                <p class="s-description text-center">
                  I create world class customised softwares that serve the market needs for businesses , startups and organisations.
                </p>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="service-box">
              <div class="service-ico">
                <span>
                    <img :src="ui" alt="ui/ux design" style="width:70px;, height:70px;" />
                </span>
              </div>
              <div class="service-content">
                <h2 class="s-title"> UI/UX Design</h2>
                <p class="s-description text-center">
                  I create web designs with great user experience, stunning graphics package 
                  alongside and they are easy to manage.
                </p>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="service-box">
              <div class="service-ico">
                <span>
                    <img :src="gis" alt="gis" style="width:70px;, height:70px;" />
                </span>
              </div>
              <div class="service-content">
                <h2 class="s-title"> GIS </h2>
                <p class="s-description text-center">
                  I produce maps and other displays of geographic information for further analysis and presentation.
                </p>
              </div>
            </div>
          </div>     
        </div>
      </div>
    </section>
</template>