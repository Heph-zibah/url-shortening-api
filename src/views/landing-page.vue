<script setup>
import Navbar from "../components/navbar.vue"
import Hero from "../components/hero.vue";
import Form from "../components/Form.vue";
import Features from "../components/Features.vue";
import CTA from "../components/CTA.vue"
import Footer from "../components/footer.vue";
</script>

<template>
    <div >
        <Navbar/>
        <main>
            <Hero/>
            <!-- <Form/> -->
            <Features/>
            <CTA/>
        </main>
        <Footer/>
    </div>
</template>