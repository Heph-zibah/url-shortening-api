<script setup>
import Button from './button.vue';
</script>

<template>
    <div class="flex flex-col md:flex-row-reverse items-center justify-between md:p-10 lg:px-20 lg:py-10 xl:max-w-[85rem] xl:mx-auto">
        <div>
            <img src="../assets/images/illustration-working.svg" alt="a lady working on a desk with a desktop in front of her">
        </div>
        <div class="mt-7 md:mt-0 mx-5 md:mx-0 text-center md:text-start md:pr-20">
            <h1 class="text-5xl text-veryDarkBlue font-bold leading-[60px] md:leading-[50px]">More than just shorter links</h1>
            <p class="my-4 md:mt-2 md:mb-5 md:w-96 text-grayishViolet">Build your brand’s recognition and get detailed insights on how your links are performing.</p>
            <Button color="cyan" size="medium">Get Started</Button>
        </div>
    </div>
</template>