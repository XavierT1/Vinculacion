<template>
  <v-container fluid class="contenedor">
    <v-card class="rounded-0 color">
      <v-row no-gutters>
        <v-col cols="12" md="6">
          <v-container class="colorF">
            <v-img alt="" class="img" src="../assets/Sevee_Logo.svg" transition="scale-transition" />
          </v-container>
        </v-col>
        <v-col cols="12" md="6">
          <v-container class="cardLogo">
            <v-img class="Ilustracion1" src="../assets/Sevee_Ilustracion.svg" transition="scale-transition" />
          </v-container>
        </v-col>
      </v-row>
    </v-card>

    <v-card flat class="rounded-0 fondoTexto">
      <v-card-text class=" white--text text">
        <p>El Sistema Ecuatoriano de Visualización de Estadística Electoral es una plataforma gratuita pensada para
          facilitar la observación dinámica de los resultados de los procesos electorales en Ecuador, garantizando el
          derecho de los ciudadanos y las ciudadanas al acceso libre a la información (Artículo 61 de la Constitución de la
          República del Ecuador). SEVEE es el resultado del trabajo conjunto entre el Instituto de Altos Estudios Nacionales 
          y la Universidad Central, con el apoyo del Ágora Ciudadana.</p>
      </v-card-text>
    </v-card>
    
    <v-card flat class="rounded-0 fondo2">
      <v-row no-gutters>
        <v-col cols="12" md="3">
          <v-card-text class="text2">
        <p>Aprende más sobre cómo funciona el Sevee.</p>
      </v-card-text>
        </v-col>
        <v-col cols="12" md="9">
      <VideoInstructivo />

        </v-col>
      </v-row>
  
      </v-card>
  
    <v-card flat class="rounded-0 fondo">
      <v-img alt="" src="../assets/Sevee_Edificios.svg" transition="scale-transition" />
    </v-card>

  </v-container>
</template>

<script>
import VideoInstructivo from './VideoInstructivo.vue';

export default {
  name: 'App',

  components: {
    VideoInstructivo
  },

  data() {
    return {
      tabs: null,
    }
  },
};
</script>

<style scoped>

.fondo2{
  /*background: linear-gradient(180deg, #1267C2 0%,  #D8EDFF 80.19%);*/
  background: linear-gradient(180deg, #fdffff 0%, #D8EDFF 60.19%);
  /*background: #D8EDFF;
  background: #1267C2;*/
  padding-top: 3%;
  padding-left: 10%;
  text-align: center;
}
.fondo {
  /*margin-top: 1px;*/
  /*background: linear-gradient(180deg, #1267C2 0%,  #D8EDFF 60.19%);
  background-image: url("https://www.youtube.com/embed/Q7xO3moljXs");*/
}

.text {
  font-family: 'Open Sans';
  font-size: 24px;
  font-weight: 300;
  line-height: 33px;
  text-align: center;
}

.text2 {
  font-family: 'Open Sans';
  font-size: 48px;
  font-weight: 600;
  line-height: 60px;
  text-align: center;
  padding-top: 50px;
  padding-left: 10px;
}


.fondoTexto {
  display: flex;
  justify-content: space-evenly;
  background: #1267C2;
  padding-left: 12%;
  padding-right: 12%;
  padding-top: 3%;
  padding-bottom: 3%;
}

.color {
  background: linear-gradient(180deg, #fdffff 0%, #D8EDFF 60.19%);
}

.contenedor {
  margin-top: 5px;
  padding: 0%;
  padding-top: 0%;
}

.cardLogo {
  max-width: 100%;
  height: auto;
  padding: 0%;
}

.colorF {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.Ilustracion1 {
  height: auto;
  max-width: 100%;
}

.img {
  
  margin: 2%;
  max-width: 90%;
  height: auto;
}

.VideoTutorial {
  margin-top: 150px;
  margin-right: 350px;
  width: 100%;
  align-content: center;
}

.cardTutorial {
  align-self: center;
  margin-left: 5%;
}
</style>