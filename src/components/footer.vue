<script setup>
</script>

<template>
    <footer class="bg-darkViolet">
        <div class="text-white grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 p-5 md:p-10 lg:px-20 lg:py-10 xl:max-w-[85rem] xl:mx-auto text-center md:text-start">
            <div>
                <h1 class="text-2xl font-bold mb-5 md:mb-0">Shortly</h1>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 text-sm gap-y-5 my-7 md:my-0">
                <ul class="space-y-3">
                    <span class="font-bold">Features</span>
                    <li><a href="#">Link Shortening</a></li>
                    <li><a href="#">Branded Links</a></li>
                    <li><a href="#">Analytics</a></li>
                </ul>
                <ul class="space-y-3">
                    <span class="font-bold">Resources</span>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Developers</a></li>
                    <li><a href="#">Support</a></li>
                </ul>
                <ul class="space-y-3">
                    <span class="font-bold">Company</span>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Our Teams</a></li>
                    <li><a href="#">Careers</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            <div class="flex items-start justify-center md:justify-end gap-3">
                <img src="../assets/images/icon-facebook.svg" alt="facebook logo" class="cursor-pointer">
                <img src="../assets/images/icon-twitter.svg" alt="twitter logo" class="cursor-pointer">
                <img src="../assets/images/icon-pinterest.svg" alt="pininterest logo" class="cursor-pointer">
                <img src="../assets/images/icon-instagram.svg" alt="instagram logo" class="cursor-pointer">
            </div>
        </div>
    </footer>
</template>