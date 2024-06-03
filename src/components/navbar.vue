<script setup>
import DropdownMenu from './dropdown-menu.vue';
import { ref, onMounted, onUnmounted } from 'vue';
import Button from './button.vue';

const dropdown = ref(false)

const toggleDropdown = () => {
    dropdown.value = !dropdown.value
}

const closeDropdown = (event) => {
    // Check if the click is outside the dropdown menu
    if (!event.target.closest('.dropdown-menu') && !event.target.closest('.fa-bars')) {
        dropdown.value = false;
    }
};

onMounted(() => {
    document.addEventListener('click', closeDropdown);
});

onUnmounted(() => {
    document.removeEventListener('click', closeDropdown);
});
</script>

<template>
    <nav class=" p-5 md:p-10 lg:px-20 lg:py-10 xl:max-w-[85rem] xl:mx-auto relative ">
        <div class="flex justify-between items-center">
            <div class="flex items-center">
                <img src="../assets/images/logo.svg" alt="shortly logo">
                <ul class="md:flex gap-5 hidden text-sm font-medium pl-5 ">
                    <li class="text-darkViolet hover:text-veryDarkViolet"><a href="#">Features</a></li>
                    <li class="text-darkViolet hover:text-veryDarkViolet"><a href="#">Pricing</a></li>
                    <li class="text-darkViolet hover:text-veryDarkViolet"><a href="#">Resources</a></li>
                </ul>
            </div>
            
            <div class="flex items-center">
                <i class="fa-solid fa-bars text-3xl md:hidden cursor-pointer" @click.stop="toggleDropdown"></i>
                
                <div class="hidden md:flex gap-5 font-medium">
                    <button class="cursor-pointer text-darkViolet hover:text-veryDarkViolet">Login</button>
                    <Button  color="cyan" size="medium">Sign up</Button>
                </div> 
            </div>
        </div>
        <DropdownMenu v-if="dropdown" class="dropdown-menu"/>
    </nav>
</template>