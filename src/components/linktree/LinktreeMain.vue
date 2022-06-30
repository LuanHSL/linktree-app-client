<template>
  <div :class="themeDefault.bgColorPage" class="container mx-auto px-4 h-screen">
    <section class="flex flex-row-reverse">
      <div>=</div>
    </section>
    <section class="flex justify-center">
      <img class="w-28 rounded-full" src="https://ovicio.com.br/wp-content/uploads/2022/03/20220320-ovicio-one-piece-anime-luffy-555x555.jpg">
    </section>
    <section class="my-3 px-4">
      <span :class="themeDefault.textPage" class="font-sans text-2xl font-bold">Confira minhas redes socias</span>
    </section>
    <section>
      <div
        v-for="socialMedia in socialMedias" :key="socialMedia.id"
        :class="[themeDefault.socialMediaOdd.bgColor, themeDefault.socialMediaOdd.bgColorHover, themeDefault.socialMediaOdd.textColor, themeDefault.socialMediaEven.bgColor, themeDefault.socialMediaEven.bgColorHover, themeDefault.socialMediaEven.textColor ]"
        class="flex items-center h-16 border border-solid rounded-xl border-transparent px-3 mb-2.5">
        <img class="w-10 mr-3" :src="socialMedia.photoURL" :alt="socialMedia.slug">
        <span class="text-xl font-semibold">{{ socialMedia.username }}</span>
      </div>
    </section>
  </div>  
</template>

<script>
export default {
  name: 'LinktreeMain',
  data() {
    return {
      socialMedias: null,
      theme: null,
    };
  },
  methods: {
    setSocialMedias() {
      this.socialMedias = [
        {
          id: 1,
          photoURL: 'https://images-na.ssl-images-amazon.com/images/I/41b3zsiq4pL.png',
          slug: 'tiktok',
          username: '@luffytaro',
        },
        {
          id: 2,
          photoURL: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/640px-Instagram_icon.png',
          slug: 'instagram',
          username: '@luffytaro',
        },
        {
          id: 3,
          photoURL: 'https://upload.wikimedia.org/wikipedia/commons/c/cd/Facebook_logo_%28square%29.png',
          slug: 'facebook',
          username: 'Monkey D. Luffy',
        },
      ];
    },
    setTheme() {
      this.themeDefault = {
        bgColorPage: 'bg-neutral-800',
        textPage: 'text-white',
        socialMediaOdd: {
          bgColor: 'odd:bg-purple-400',
          bgColorHover: 'odd:hover:bg-purple-500',
          textColor: 'odd:text-gray-800',
        },
        socialMediaEven: {
          bgColor: 'even:bg-indigo-400',
          bgColorHover: 'even:hover:bg-indigo-500',
          textColor: 'even:text-gray-800',
        },
      };
    },
  },
  beforeMount() {
    this.setSocialMedias();
    this.setTheme();
  },
};
</script>

<style scoped>

</style>