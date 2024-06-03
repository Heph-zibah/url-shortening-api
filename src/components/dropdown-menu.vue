<script setup>
import Button from './button.vue';
</script>

<template>
    <div class="absolute md:hidden  left-0 right-0 top-16 rounded-xl mx-5 bg-darkViolet py-5">
        <div class="text-center space-y-6">
            <ul class="font-medium text-white border-b-gray border-b mx-5 pb-5 space-y-5">
                <li><a href="#">Features</a></li>
                <li><a href="#">Pricing</a></li>
                <li><a href="#">Resources</a></li>
            </ul>
            <div class="text-white flex flex-col gap-5 font-medium">
                <button class="">Login</button>
                <Button color="cyan" size="medium" class="mx-5">Sign up</Button>
            </div>
        </div>
    </div>
</template>