<template>
  <v-container fluid class="contenedor">
    <v-row no-gutters>
      <v-card flat color="c-Inicio" width="100%">

        <v-window touchless v-model="onboarding">
          <v-window-item :value="0">
            <div>
              <MapaExtranjero v-bind:expand_b=this.boolean1 @add2="(i) => numero_vuelta_e = i"></MapaExtranjero>
            </div>
          </v-window-item>

          <v-window-item :value="1">
            <div class="size">
              <div class="d-flex justify-center mb-6 size" v-if="numero_vuelta_e == 0">
                <CodGraficose />
              </div>
              <div class="d-flex justify-center mb-6 size" v-else>
                <CodGraficos2e />
              </div>
            </div>
          </v-window-item>

          <v-window-item :value="2">

            <div class="size">
              <div class="d-flex justify-center mb-6 size" v-if="numero_vuelta_e == 0">
                <CodTablas v-bind:zona="'e'" v-bind:vuelta=1></CodTablas>
              </div>
              <div class="d-flex justify-center mb-6 size" v-else>
                <CodTablas v-bind:zona="'e'" v-bind:vuelta=2></CodTablas>
              </div>
              <!--<CodTablas :id_1 = "numero_vuelta_e" v-bind:key = "numero_vuelta_e"/>-->
              
            </div>
          </v-window-item>

        </v-window>
      
        <v-divider></v-divider>

        <v-card-actions background-color="white" class="justify-space-between">
          <v-btn text @click="prev">
            <v-icon>mdi-chevron-left</v-icon>
          </v-btn>
          <v-item-group v-model="onboarding" class="text-center" mandatory>
            <v-item v-for="n in length" :key="`btn-${n}`" v-slot="{ active, toggle }">
              <v-btn :input-value="active" icon @click="toggle">
                <v-icon>mdi-record</v-icon>
              </v-btn>
            </v-item>
          </v-item-group>
          <v-btn text @click="next">
            <v-icon>mdi-chevron-right</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-row>

    <v-row no-gutters gutters class="margen" v-if="numero_vuelta_e == 0">
      <InfoGeneral />
    </v-row>
    <v-row no-gutters class="margen" v-else>
      <InfoGeneral2 />
    </v-row>

  </v-container>
</template>
  
<script>
import InfoGeneral from '@/modules/2017/components/InfoGeneral.vue';
import InfoGeneral2 from '@/modules/2017/components/InfoGeneral2.vue';
import CodGraficose from '@/modules/2017/components/CodGraficose.vue';
import CodGraficos2e from '@/modules/2017/components/CodGraficos2e.vue';
import CodTablas from '@/modules/2017/components/CodTablas.vue';
import MapaExtranjero from '@/modules/2017/components/MapaExtranjero.vue';

export default {
  name: "VotantesExtranjeros2017",
  data: () => {

    return {
      length: 3,
      onboarding: 0,
      boolean1: true,
      ruleta: 0,
      numero_vuelta_e: 0,
      idMapa1: "API_1",
      idMapa2: "API_2",
    }

  },
  methods: {
    next() {
      this.onboarding = this.onboarding + 1 === this.length
        ? 0
        : this.onboarding + 1
    },
    prev() {
      this.onboarding = this.onboarding - 1 < 0
        ? this.length - 1
        : this.onboarding - 1
    },
  },
  components: { CodGraficose, CodGraficos2e, CodTablas, MapaExtranjero, InfoGeneral, InfoGeneral2 }

}
</script>
  
<style scoped>
.size {
  height: 650px;
}
</style>
