<script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  
  let show = ref(false);

  let active_link = ref("hero")

  let adjustHeight = ref(false)

  const windowWidth = ref(window.innerWidth);
  // Update window width when the component is mounted
  onMounted(() => {
    const handleResize = () => {
      windowWidth.value = window.innerWidth;
      if(window.innerWidth > 991){
        show.value = false
      }
    };

    const handleScroll = () => {
        let height = window.scrollY
        if(height > 10){
            adjustHeight.value = true
        }else{
            adjustHeight.value = false
        }
        handleActiveLinks()
    }

    const removeClassLists = (id) => {
      let navlinks = document.querySelectorAll('nav-link')

    }

    const handleActiveLinks = () => {
      const isNullOrUndefined = (value) => {
        return value === null || value === undefined;
      }
      const ids = ['hero', 'about', 'services', 'work', 'contact'];
      for(const id of ids){
        const link = document.getElementById(id)
        if(!isNullOrUndefined(link)){
          const rect = link.getBoundingClientRect()
          if(rect.top <= 0 && rect.bottom > 0){
            active_link.value = id
            // switch(id){
            //   case 'about':
            //     document.querySelector('a[href="#about"]').classList.add('active')
            //     // console.log("link:", navlink)
            // }
            // link.classList.add("active")
          }
        }
      }
    }

    // Attach event listener for scroll
    window.addEventListener('scroll', handleScroll)

    // Attach event listener for window resize
    window.addEventListener('resize', handleResize);

    // Clean up the event listener when the component is unmounted
    onBeforeUnmount(() => {
      window.removeEventListener('resize', handleResize);
      window.removeEventListener('scroll', handleScroll);
    });
  });

  const toggleMenu = (value) => {
    show.value = value
  }
  
</script>

<template>
  <header id="header" :class="{'fixed-top header-isActive': show, 'fixed-top header-height':!show, 'scroll-background':adjustHeight}">
      <div :class="{'container-isActive container d-flex': show, 'container d-flex align-items-end':!show}">
        <div v-if="windowWidth < 991" :class="{'window-isActive':show}">
          <div v-if="!show">
            <button class="custom-button" @click="toggleMenu(true)">
              <i class="bi bi-list" :style="{fontSize: '3rem', color:'#fff'}"></i>
            </button>
          </div>
          <div v-if="show" style="height: 100%">
            <button class="custom-button" @click="toggleMenu(false)">
              <i class="bi bi-x-lg" :style="{fontSize: '3rem', color:'#fff'}"></i>
            </button>
            <ul class="listContainer">
              <li>
                <a :class="{'nav-link scrollto':active_link !== 'hero', 'nav-link scrollto active': active_link === 'hero'}" href="#hero">Home</a>
              </li>
              <li>
                <a :class="{'nav-link scrollto':active_link !== 'about', 'nav-link scrollto active': active_link === 'about'}" href="#about">About</a>
              </li>
              <li>
                <a :class="{'nav-link scrollto':active_link !== 'services', 'nav-link scrollto active': active_link === 'services'}" href="#services">Services</a>
              </li>
              <li>
                <a :class="{'nav-link scrollto':active_link !== 'work', 'nav-link scrollto active': active_link === 'work'}" href="#work">Portfolio</a>
              </li>             
              <li>
                <a :class="{'nav-link scrollto':active_link !== 'contact', 'nav-link scrollto active': active_link === 'contact'}" href="#contact">Contact</a>
              </li>
            </ul>
          </div>
        </div>
        <nav id="navbar" class="navbar text-end">
          <ul>
            <li>
              <a :class="{'nav-link scrollto':active_link !== 'hero', 'nav-link scrollto active': active_link === 'hero'}" href="#hero">Home</a>
            </li>
            <li>
              <a :class="{'nav-link scrollto':active_link !== 'about', 'nav-link scrollto active': active_link === 'about'}" href="#about">About</a>
            </li>
            <li>
              <a :class="{'nav-link scrollto':active_link !== 'services', 'nav-link scrollto active': active_link === 'services'}" href="#services">Services</a>
            </li>
            <li>
              <a :class="{'nav-link scrollto':active_link !== 'work', 'nav-link scrollto active': active_link === 'work'}" href="#work">Portfolio</a>
            </li>             
            <li>
              <a :class="{'nav-link scrollto':active_link !== 'contact', 'nav-link scrollto active': active_link === 'contact'}" href="#contact">Contact</a>
            </li>
          </ul>
        </nav>
      </div>
  </header>
</template>

<style scoped>
.custom-button{
  background: transparent;
  border: none;
}
.header-height{
  height: 8rem;
}
.header-isActive{
  padding: 0;
    background: black;
    height: 90vh;
    width: 30%;
}
.container-isActive{
  margin: 0;
    height: 100%;
}
.window-isActive{
  width: 100%;
}
.listContainer{
  padding: 0;
    height: 80%;
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}
.listContainer > li{
  font-size: 2rem;
}

.scroll-background{
  background: black;
}
</style>