<template>
  <v-card color="#12A2C2 " class="InfoCard">
    <v-row no-gutters>
      <v-col cols="12" md="4">
        <v-card-text class="titulo">
          Información General
        </v-card-text>
      </v-col>

      <v-col cols="12" md="8">
        <v-container class="container-datos">
          <div class="datos">
            <v-img alt="" class="img" src="../assets/ausentes.svg" transition="scale-transition" />
            <div >{{ sufragantes }}</div>
            <div >Sufragantes</div>
          </div>
          <div class="datos">
            <v-img alt="" class="img" src="../assets/ausentes.svg" transition="scale-transition" />
            <div class="d-flex justify-center">{{ ausentes }}</div>
            <div class="d-flex justify-center">Ausentes</div>
          </div>
          <div class="datos">
            <v-img alt="" class="img" src="../assets/ausentes.svg" transition="scale-transition" />
            <div class="d-flex justify-center">{{ femenino }}</div>
            <div class="d-flex justify-center">Femenino</div>
          </div>
          <div class="datos">
            <v-img alt="" class="img" src="../assets/ausentes.svg" transition="scale-transition" />
            <div class="d-flex justify-center">{{ masculino }}</div>
            <div class="d-flex justify-center">Masculino</div>
          </div>
        </v-container>

      </v-col>

    </v-row>
  </v-card>
</template>

<script>
export default {
  name: "InfoGeneral",
  components: {},
  data() {
    return {
      vuelta: null,
      ausentes: 2491194,
      sufragantes: 10235781,
      masculino: 3273067,
      femenino: 4471520,
    };
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

.img {
  width: 60px;
  height: auto;

}
.container-datos{
  padding-left: 10%;
  padding-right: 10%;
  justify-content: space-between;
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.InfoCard {
  margin: 0%;
  padding: 0%;
  width: 100%;
  height: auto;
  border-radius: 0px;
}

.titulo {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  color: white;
  font-size: 36px;
  font-family: "Oswald";
  line-height: normal;
}

.datos {
  padding: 1%;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: "Open Sans", sans-serif;
  font-size: 24px;
}
</style>