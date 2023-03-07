<template>
    <div>
        <div v-if="prop == 1" class="d-flex flex-column">
            <div v-if="prop2 == 1">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Convivencia ciudadana
                        </span>
                    </h3>
                </div>
                <CpConvivenciaCiudadana :usuario="usuario" />
            </div>
            <div v-if="prop2 == 2">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Diversidad y género
                        </span>
                    </h3>
                </div>
                <CpDiversidadGenero :usuario="usuario" />
            </div>
            <div v-if="prop2 == 3">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Gestión humana
                        </span>
                    </h3>
                </div>
                <CpGestionHumana :usuario="usuario" />
            </div>
            <div v-if="prop2 == 4">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Hacienda y contratación
                        </span>
                    </h3>
                </div>
                <CpHaciendaContratacion :usuario="usuario" />
            </div>
            <div v-if="prop2 == 5">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Inclusión social
                        </span>
                    </h3>
                </div>
                <CpInclusionSocial :usuario="usuario" />
            </div>
            <div v-if="prop2 == 6">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Salud
                        </span>
                    </h3>
                </div>
                <CpSalud :usuario="usuario" />
            </div>
            <div v-if="prop2 == 7">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seguridad vial
                        </span>
                    </h3>
                </div>
                <CpSeguridadVial :usuario="usuario" />
            </div>
            <div v-if="prop2 == 8">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seguridad y salud en el trabajo
                        </span>
                    </h3>
                </div>
                <CpSeguridadSaludTrabajo :usuario="usuario" />
            </div>
            <div v-if="prop2 == 9">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seminarios
                        </span>
                    </h3>
                </div>
                <CpSeminarios :usuario="usuario" />
            </div>
            <div v-if="prop2 == 10">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Social
                        </span>
                    </h3>
                </div>
                <CpSocial :usuario="usuario" />
            </div>
            <div v-if="prop2 == 11">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Tecnología e innovación
                        </span>
                    </h3>
                </div>
                <CpTecnologiaInnovacion :usuario="usuario" />
            </div>
            <div @click="salir" class="d-flex justify-content-center m-2">
                <button class="index-cursos-button-salir">
                    VER MENOS CURSOS
                </button>
            </div>
        </div>
        <div v-if="prop == 2" class="d-flex flex-column">
            <div v-if="prop2 == 1">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Convivencia ciudadana
                        </span>
                    </h3>
                </div>
                <CpConvivenciaCiudadana :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 2">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Diversidad y género
                        </span>
                    </h3>
                </div>
                <CpDiversidadGenero :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 3">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Gestión humana
                        </span>
                    </h3>
                </div>
                <CpGestionHumana :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 4">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Hacienda y contratación
                        </span>
                    </h3>
                </div>
                <CpHaciendaContratacion :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 5">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Inclusión social
                        </span>
                    </h3>
                </div>
                <CpInclusionSocial :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 6">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Salud
                        </span>
                    </h3>
                </div>
                <CpSalud :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 7">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seguridad vial
                        </span>
                    </h3>
                </div>
                <CpSeguridadVial :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 8">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seguridad y salud en el trabajo
                        </span>
                    </h3>
                </div>
                <CpSeguridadSaludTrabajo :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 9">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Seminarios
                        </span>
                    </h3>
                </div>
                <CpSeminarios :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 10">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Social
                        </span>
                    </h3>
                </div>
                <CpSocial :usuario="usuario2" />
            </div>
            <div v-if="prop2 == 11">
                <div class="mb-4">
                    <h3 class="text-center">
                        <span class="index-cursos-titulo">
                            Tecnología e innovación
                        </span>
                    </h3>
                </div>
                <CpTecnologiaInnovacion :usuario="usuario2" />
            </div>
            <div @click="salir" class="d-flex justify-content-center m-2">
                <button class="index-cursos-button-salir">
                    VER MENOS CURSOS
                </button>
            </div>
        </div>
    </div>
</template>

<script>
import datos from '../assets/cursos.json'
import CpConvivenciaCiudadana from './SubCursos/CpConvivenciaCiudadana.vue'
import CpDiversidadGenero from './SubCursos/CpDiversidadGenero.vue'
import CpGestionHumana from './SubCursos/CpGestionHumana.vue'
import CpHaciendaContratacion from './SubCursos/CpHaciendaContratacion.vue'
import CpInclusionSocial from './SubCursos/CpInclusionSocial.vue'
import CpSalud from './SubCursos/CpSalud.vue'
import CpSeguridadVial from './SubCursos/CpSeguridadVial.vue'
import CpSeguridadSaludTrabajo from './SubCursos/CpSeguridadSaludTrabajo.vue'
import CpSeminarios from './SubCursos/CpSeminarios.vue'
import CpSocial from './SubCursos/CpSocial.vue'
import CpTecnologiaInnovacion from './SubCursos/CpTecnologiaInnovacion.vue'

export default {
  name: 'CpTecnologia',
  data () {
    return {
      cursos: datos,
      usuario: 1,
      usuario2: 2
    }
  },
  components: {
    CpConvivenciaCiudadana,
    CpDiversidadGenero,
    CpGestionHumana,
    CpHaciendaContratacion,
    CpInclusionSocial,
    CpSalud,
    CpSeguridadVial,
    CpSeguridadSaludTrabajo,
    CpSeminarios,
    CpSocial,
    CpTecnologiaInnovacion
  },
  props: {
    prop: {
      type: Number
    },
    prop2: {
      type: Number
    }
  },
  methods: {
    salir () {
      this.$emit('salir')
    }
  }
}
</script>
