<template>
   <ion-page>
      <ion-header>
         <ion-toolbar>
            <ion-title>Tab 2</ion-title>
         </ion-toolbar>
      </ion-header>
      <ion-content :fullscreen="true">
         <ion-button @click="sayCheese">Say Cheese!</ion-button>
         <p>
            <img ref="image" :src="imageWebPath || 'javascript:void(0)'"
            alt="[no image]"
            style="min-height: 300px; width: 98%; border: 1px dotted green;">
            <br>
            <div style="border: 1px solid blue;">{{ message }}</div>
        </p>
      </ion-content>
   </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton } from '@ionic/vue';
import { Camera, CameraResultType } from '@capacitor/camera';
import { ref } from 'vue';

let imageWebPath = ref('');
let message = ref('[no message]');

async function sayCheese(/*event*/) {
   try {
      const photo = await Camera.getPhoto({
         resultType: CameraResultType.DataUrl,
      })
      console.log(photo);
      imageWebPath.value = photo.dataUrl || '';
      message.value = imageWebPath.value || '[no data]`';
   }
   catch (error:any) {
      message.value = error.toString();
   }
}
</script>
