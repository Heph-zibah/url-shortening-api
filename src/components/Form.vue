<script setup>
import Button from './button.vue';
import { ref, onMounted } from 'vue';

const url = ref('')
const error = ref('')
const shortenedUrls = ref([])

onMounted(() => {
  const storedUrls = localStorage.getItem('shortenedUrls')
  if (storedUrls) {
    shortenedUrls.value = JSON.parse(storedUrls)
  }
})

const shortenUrl = () => {
  error.value = ''
  if (!url.value) {
    error.value = 'Please add a link'
    return
  }

  const shortened = `https://rel.ink/${Math.random().toString(36).substring(2, 8)}`
  shortenedUrls.value.push({ original: url.value, shortened })

  localStorage.setItem('shortenedUrls', JSON.stringify(shortenedUrls.value))

  url.value = ''
}

const copyToClipboard = (text, index) => {
  navigator.clipboard.writeText(text).then(() => {
    shortenedUrls.value[index].copied = true
    localStorage.setItem('shortenedUrls', JSON.stringify(shortenedUrls.value))

    setTimeout(() => {
      shortenedUrls.value[index].copied = false
      localStorage.setItem('shortenedUrls', JSON.stringify(shortenedUrls.value))
    }, 2000)
  })
}

const deleteUrl = (index) => {
  shortenedUrls.value.splice(index, 1)
  localStorage.setItem('shortenedUrls', JSON.stringify(shortenedUrls.value))
}
</script>

<template>
   <section class="-mt-40 px-5 md:m-10 lg:px-20 lg:pb-10 xl:max-w-[85rem] xl:mx-auto">
     <div class="">
        <div class="text-white bg-darkViolet bg-desktop bg-center bg-no-repeat bg-cover text-center relative  rounded-xl py-10 mb-4">
        
        <div class="">
            <form action="" class="flex flex-col md:flex-row px-10 gap-5 space-y-3 md:space-y-0" @submit.prevent="shortenUrl">
                <input type="text" class="w-full rounded-lg p-4 placeholder:text-lg text-darkViolet" placeholder="Shorten a link here" v-model="url" :class="{'outline-red border border-red' : error}">
                <Button color="cyan" size="medium" base="rounded-lg" class="w-full lg:w-1/5 font-bold" type="submit">Shorten it</Button>
                <p v-if="error" class="text-red absolute bottom-[105px] md:bottom-7">{{ error }}</p>
            </form>
        </div>
       
    </div>
     <div class=" relative" v-if="shortenedUrls.length">
            <div class="flex justify-between md:items-center flex-col md:flex-row bg-white px-5 md:px-10 py-3 mb-3 rounded-lg" v-for="(item, index) in shortenedUrls" :key="index">
                <div class="text-ellipsis shorten">
                    <span class="text-darkViolet font-bold text-ellipsis ellipsis"> {{ item.original }}</span>
                </div>
                <div class="gap-x-5 flex flex-col md:flex-row mt-5">
                    <a :href="item.shortened" class="text-cyan font-bold" target="_blank">{{ item.shortened }}</a>
                     <Button color="cyan" size="medium" base="rounded-lg" class="" @click="copyToClipboard(item.shortened, index)"   :class="['p-2 rounded', item.copied ? 'bg-darkViolet text-white' : 'bg-gray-200']">{{ item.copied ? 'Copied!' : 'Copy' }}</Button>
                     
                     <div class="absolute right-0 -top-3 -mr-4 cursor-pointer">
                        <i class="fa-solid fa-delete-left text-3xl text-red" aria-hidden="true" @click="deleteUrl(index)"></i>
                     </div>
                </div>
               
            </div>
           
        </div>
    </div>
   </section>
</template>

<style>
.shorten {
    width:500px;
    white-space:nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

</style>