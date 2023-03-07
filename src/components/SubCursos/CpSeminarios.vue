<template>
    <div>
        <div v-if="usuario == 1" class="d-flex flex-wrap justify-content-center">
            <div v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                <div v-if="cursoseminarios.estado == 'activo' && cursoseminarios.usuario == 1" class="accordion-item index-cursos-accordion">
                    <h2 class="accordion-header" id="acordion1">
                        <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                            <img :src="cursoseminarios.imagen" alt="foto" class="rounded" width="300px">
                            <p class="index-cursos-titulo-accordion">
                                <strong>{{ cursoseminarios.nombre }}</strong>
                            </p>
                            <span>Conoce Más...</span>
                        </button>
                    </h2>
                    <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                        <div class="index-cursos-cuerpo-accordion">
                            <div class="d-flex align-items-center">
                                {{ cursoseminarios.contenido }}
                            </div>
                            <div class="d-flex justify-content-center">
                                <a :href="cursoseminarios.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div v-if="usuario == 2" class="d-flex flex-wrap justify-content-center">
            <div v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                <div v-if="cursoseminarios.estado == 'activo' && (cursoseminarios.usuario == 1 || cursoseminarios == 2)" class="accordion-item index-cursos-accordion">
                    <h2 class="accordion-header" id="acordion1">
                        <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                            <img :src="cursoseminarios.imagen" alt="foto" class="rounded" width="300px">
                            <p class="index-cursos-titulo-accordion">
                                <strong>{{ cursoseminarios.nombre }}</strong>
                            </p>
                            <span>Conoce Más...</span>
                        </button>
                    </h2>
                    <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                        <div class="index-cursos-cuerpo-accordion">
                            <div class="d-flex align-items-center">
                                {{ cursoseminarios.contenido }}
                            </div>
                            <div class="d-flex justify-content-center">
                                <a :href="cursoseminarios.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
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
  name: 'CpSeminarios',
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
