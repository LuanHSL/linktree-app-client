<template>
  <main class="flex justify-center">
    <!-- <QRCode /> -->
    <LinktreeMain />
  </main>
</template>

<script>
// import QRCode from './components/QRCode.vue';
import LinktreeMain from './components/linktree/LinktreeMain.vue';

export default {
  name: 'App',
  components: {
    // QRCode,
    LinktreeMain,
  },
};
</script>

<style>
</style>
