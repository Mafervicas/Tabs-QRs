<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 2</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 2</ion-title>
        </ion-toolbar>
      </ion-header>
        

      <div class="Scan">
        <StreamBarcodeReader
    @decode="onDecode"
    @loaded="onLoaded">
    </StreamBarcodeReader> 

<ImageBarcodeReader
    @decode="onDecode"
    @error="onError"
></ImageBarcodeReader>

</div>


    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import { StreamBarcodeReader } from "vue-barcode-reader";
import { ImageBarcodeReader } from "vue-barcode-reader";


export default  {
  name: 'Tab2',
  components: { 
    IonHeader, 
    IonToolbar, 
    IonTitle, 
    IonContent, 
    IonPage,
    StreamBarcodeReader,
     ImageBarcodeReader },
    methods: {
  onDecode (result) {
    console.log(result)
  },
  onLoaded (result){
console.log(result)
  },
  onError(result){
console.log(result)
  }
}
}

</script>

.Scan{
  padding-top: 70px;
  width: 400px;
  margin-left: auto;
  margin-right: auto;
}