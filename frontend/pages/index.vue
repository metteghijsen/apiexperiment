<template>
  <div class="flex justify-center items-center flex-col h-full w-full mt-[100px]">
    <img :src="dogImageUrl" alt="Random Dog Image" class="h-[350px] w-auto">
    <button class="bg-blue-900 px-8 py-4 text-white rounded-3xl my-4 font-semibold text-xl" @click="getNewDogImage">
      Nieuwe hond!
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      dogImageUrl: ''
    }
  },
  mounted () {
    this.getNewDogImage()
  },
  methods: {
    async getNewDogImage () {
      const response = await fetch('https://dog.ceo/api/breeds/image/random')
      const data = await response.json()
      this.dogImageUrl = data.message
    }
  }
}
</script>

<style>
button {
  font-family: Poppins;
}
</style>
