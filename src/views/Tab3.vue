<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 3</ion-title>
        </ion-toolbar>
      </ion-header>
      <div>
        <p class="error">{{ error }}</p>

        <p class="decode-result">Last result: <b>{{ result }}</b></p>

        <qrcode-stream @decode="onDecode" @init="onInit"></qrcode-stream>
      </div>

    </ion-content>
  </ion-page>
</template>

<script>
  import {QrcodeStream} from 'vue-qrcode-reader'


  import {
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent
  } from '@ionic/vue';

  export default {
    name: 'Tab3',

    components: {
      IonHeader,
      IonToolbar,
      IonTitle,
      IonContent,
      IonPage,
      QrcodeStream
    },
    data() {
      return {
        result: '',
        error: ''
      }
    },
    methods: {
      onDecode(result) {
        console.log('Prueebaaaa');
      },

      async onInit(promise) {
        promise.then(console.log('Then')).catch(console.log('Error'));
      }
    }
  };
</script>

<style scoped>
  .error {
    font-weight: bold;
    color: red;
  }
</style>
