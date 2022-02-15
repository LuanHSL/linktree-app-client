<template>
  <div>
    <h1>{{ title }}</h1>
    <input type="text" size="25" placeholder="Digite para gerar..." v-model="text" />

    <div v-if="text">
      <img :src="newQRCode" alt="QRCode" />
    </div>
  </div>
</template>

<script>
import QRious from 'qrious';

export default {
  name: 'QRCode', 
  data() {
    return {
      title: 'Gerador de QR Code',
      text: 'https://google.com.br/',
      qrcode: new QRious({ size: 300 }),
    };
  },
  computed: {
    newQRCode() {
      this.setQRCodeValue();
      return this.qrcode.toDataURL();
    },
  },
  methods: {
    setQRCodeValue() {
      this.qrcode.value = this.text;
    },
  },
};
</script>

<style scoped>

</style>