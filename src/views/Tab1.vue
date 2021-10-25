<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
      <div class="CodigoQr">
      <qrcode-vue :value="value" :size="size" level="H" />
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import QrcodeVue from 'qrcode.vue'
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';



export default  {
  data() {
      return {
        value: 'https://www.canva.com/',
        size: 300,
      }
    },
  name: 'Tab1',
  components: {  IonHeader, 
                 IonToolbar, 
                 IonTitle,
                 QrcodeVue, 
                 IonContent, 
                 IonPage }
}
</script>

<style scoped>
.CodigoQr{
  padding-top: 70px;
  width: 400px;
  margin-left: auto;
  margin-right: auto;
}
</style>