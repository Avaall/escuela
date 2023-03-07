<template>
    <div>
        <div v-if="usuario == 1" class="d-flex flex-wrap justify-content-center">
            <div v-for="(cursoConvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoConvivenciaCiudadana.id">
                <div v-if="cursoConvivenciaCiudadana.estado == 'activo' && cursoConvivenciaCiudadana.usuario == 1" class="accordion-item index-cursos-accordion">
                    <h2 class="accordion-header" id="acordion1">
                        <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                            <img :src="cursoConvivenciaCiudadana.imagen" alt="foto" class="rounded" width="300px">
                            <p class="index-cursos-titulo-accordion">
                                <strong>{{ cursoConvivenciaCiudadana.nombre }}</strong>
                            </p>
                            <span>Conoce Más...</span>
                        </button>
                    </h2>
                    <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                        <div class="index-cursos-cuerpo-accordion">
                            <div class="d-flex align-items-center">
                                {{ cursoConvivenciaCiudadana.contenido }}
                            </div>
                            <div class="d-flex justify-content-center">
                                <a :href="cursoConvivenciaCiudadana.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div v-if="usuario == 2" class="d-flex flex-wrap justify-content-center">
            <div v-for="(cursoConvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoConvivenciaCiudadana.id">
                <div v-if="cursoConvivenciaCiudadana.estado == 'activo' && (cursoConvivenciaCiudadana.usuario == 1 || cursoConvivenciaCiudadana == 2)" class="accordion-item index-cursos-accordion">
                    <h2 class="accordion-header" id="acordion1">
                        <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                            <img :src="cursoConvivenciaCiudadana.imagen" alt="foto" class="rounded" width="300px">
                            <p class="index-cursos-titulo-accordion">
                                <strong>{{ cursoConvivenciaCiudadana.nombre }}</strong>
                            </p>
                            <span>Conoce Más...</span>
                        </button>
                    </h2>
                    <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                        <div class="index-cursos-cuerpo-accordion">
                            <div class="d-flex align-items-center">
                                {{ cursoConvivenciaCiudadana.contenido }}
                            </div>
                            <div class="d-flex justify-content-center">
                                <a :href="cursoConvivenciaCiudadana.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import datos from '../../assets/cursos.json'

export default {
  name: 'CpConvivenciaCiudadana',
  data () {
    return {
      cursos: datos
    }
  },
  props: {
    usuario: {
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
