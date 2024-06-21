<script setup>
import Form from './Form.vue';
</script>

<template>
    <section class="bg-gray bg-opacity-25 -pt-40">
        <Form/>
        <div class=" px-5 py-10 md:p-10 lg:px-20 lg:pt-10 lg:pb-20 xl:max-w-[85rem] xl:mx-auto ">
            <div class="text-center max-w-md mx-auto">
                <h2 class="text-3xl font-bold text-veryDarkBlue ">Advanced Statistics</h2>
                <p class="text-grayishViolet font-bold mt-2"> Track how your links are performing across the web with our advanced statistics dashboard.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-y-16 md:gap-8 mt-10 relative text-center md:text-start">
                <div class="bg-white rounded-lg py-5 px-7">
                    <div class="bg-veryDarkViolet rounded-full p-2 w-fit -mt-8 mx-auto md:mx-0">
                        <img src="../assets/images/icon-brand-recognition.svg" alt=""  class="w-7">
                    </div>
                <div class="pt-5">
                        <strong class="text-lg">Brand Recognition</strong>
                        <p>Boost your brand recognition with each click. Generic links don’t mean a thing. Branded links help instill confidence in your content.</p>
                </div>
                
                </div>
                <div class="h-1/2 w-2 md:w-1/2 md:h-3 bg-cyan absolute left-[50%] top-40 md:left-[380px]  md:top-20 -z-10"></div>
                <div class="bg-white rounded-lg py-5 px-7 md:mt-5 md:-mb-5">
                    <div class="bg-veryDarkViolet rounded-full p-2 w-fit -mt-8 mx-auto md:mx-0">
                        <img src="../assets/images/icon-detailed-records.svg" alt="" class="w-7">
                    </div>
                    <div class="pt-5">
                        <strong class="text-lg">Detailed Records</strong>
                        <p>Gain insights into who is clicking your links. Knowing when and where people engage with your content helps inform better decisions.</p>
                    </div>
                </div>
                <!-- <div class="h-40 w-2 md:w-40 md:h-3 bg-cyan absolute left-[50%] md:right-[590px] top-20 "></div> -->
                <div class="bg-white rounded-lg py-5 px-7 md:mt-10 md:-mb-10">
                    <div class="bg-veryDarkViolet rounded-full p-2 w-fit -mt-10 mx-auto md:mx-0">
                        <img src="../assets/images/icon-fully-customizable.svg" alt="" class="w-7">
                    </div>
                    <div class="pt-5">
                        <strong class="text-lg">Fully Customizable </strong>
                        <p>Improve brand awareness and content discoverability through customizable links, supercharging audience engagement.</p>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>