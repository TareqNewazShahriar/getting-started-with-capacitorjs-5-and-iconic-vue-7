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

      <ion-range style="margin: 20px;"></ion-range>
      <br>
      <ion-toggle>Default Toggle</ion-toggle><br /><br />
      <ion-toggle :checked="true">Checked Toggle</ion-toggle><br /><br />
      <ion-toggle :disabled="true">Disabled Toggle</ion-toggle><br /><br />
      <ion-toggle :checked="true" :disabled="true">Disabled Checked Toggle</ion-toggle>

      <br>

      <ion-button id="present-alert">Click Me</ion-button>
      <ion-alert
        trigger="present-alert"
        header="Alert"
        sub-header="Important message"
        message="This is an alert!"
        :buttons="alertButtons"
      ></ion-alert>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonToggle, IonRange, IonAlert, IonButton, IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
const alertButtons = ['OK'];
</script>
