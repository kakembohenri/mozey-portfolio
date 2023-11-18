<script setup>
    import Navbar from '../../components/navbar/navbar.vue';
    import Intro from "../intro/index.vue"
    import About from "../about/index.vue"
    import Services from "../services/index.vue"
    import Portfolio from "../portfolio/index.vue"
    import Testimonies from "../testimonies/index.vue"
    import Contact from "../contact/index.vue"
    import Footer from "../footer/index.vue"

</script>
<template>
    <Navbar />
    <Intro />
    <main id="main">
        <About />
        <Services />
        <Portfolio />
        <Testimonies />
    </main>
    <Contact />
    <Footer />
    <a href="#" class="back-to-top d-flex align-items-center justify-content-center">
        <i class="bi bi-arrow-up-short"></i>
    </a>
</template>