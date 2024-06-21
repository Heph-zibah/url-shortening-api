<script setup>
import Button from './button.vue';</script>

<template>
    <div class="text-white bg-[url('../assets/images/bg-boost-desktop.svg')] bg-no-repeat bg-cover bg-center bg-darkViolet  text-center relative">
        <div class="absolute left-0 right-0 top-[40%]">
            <h3 class="font-bold text-3xl mb-5">Boost your links today</h3>
            <Button color="cyan" size="medium">Get Started</Button>
        </div>
        <img src="../assets/images/bg-boost-desktop.svg" alt="" class="hidden md:block w-full" >
        <img src="../assets/images/bg-boost-mobile.svg" alt="" class="md:hidden">
    </div>
</template>