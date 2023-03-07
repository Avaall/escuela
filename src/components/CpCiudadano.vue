<template>
    <div>
        <div v-if="CursosCompletos != 0">
            <CpSubCursos :prop="usuario" :prop2="CursosCompletos" @salir="salir" />
        </div>
        <div v-else>
            <!-- 0 -->
            <div v-if="propt == 0" class="text-center">
                <div class="index-cursos-ciudadano-categoria">
                    <span class="material-symbols-outlined index-cursos-titulo">
                        arrow_back
                    </span>
                    &nbsp;Bienvenido, selecciona la categoría de tu interés
                </div>
                <img src="../assets/img/index-cursos.png" alt="" width="500px">
            </div>
            <!-- 1 -->
            <div v-if="propt == 1" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Convivencia ciudadana</span>
                    </h3>
                </div>
                <div class="d-flex flex-row flex-wrap justify-content-center">
                    <div v-for="(cursoConvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoConvivenciaCiudadana.id">
                        <div v-if="cursoConvivenciaCiudadana.estado == 'activo' && cursoConvivenciaCiudadana.usuario == 1 && cursoConvivenciaCiudadana.numeroCurso <= (cantidadCursos + 4)" class="accordion-item index-cursos-accordion">
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
                                </div>
                            </div>
                        </div>
                    </div>
                    <div v-if="Object.keys(cursos.convivenciaCiudadana).length > 3">
                        <div class="text-center m-2">
                            <button v-on:click="explorar(1)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                        </div>
                    </div>
                </div>
            </div>
            <!-- 2 -->
            <div v-if="propt == 2" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Diversidad y género</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoDiversidadGenero, identificador) in cursos.diversidadGenero" :key="cursoDiversidadGenero.id">
                        <div v-if="cursoDiversidadGenero.estado == 'activo' && cursoDiversidadGenero.usuario == 1 && cursoDiversidadGenero.numeroCurso <= (cantidadCursos + 10003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoDiversidadGenero.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoDiversidadGenero.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoDiversidadGenero.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursoDiversidadGenero.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.diversidadGenero).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(2)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 3 -->
            <div v-if="propt == 3" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Gestión humana</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoGestionHumana, identificador) in cursos.gestionHumana" :key="cursoGestionHumana.id">
                        <div v-if="cursoGestionHumana.estado == 'activo' && cursoGestionHumana.usuario == 1 && cursoGestionHumana.numeroCurso <= (cantidadCursos + 20006)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoGestionHumana.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoGestionHumana.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoGestionHumana.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursoGestionHumana.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- <div v-if="Object.keys(cursos.gestionHumana).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(3)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div> -->
            </div>
            <!-- 4 -->
            <div v-if="propt == 4" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Hacienda y contratación</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursohaciendaContratacion, identificador) in cursos.haciendaContratacion" :key="cursohaciendaContratacion.id">
                        <div v-if="cursohaciendaContratacion.estado == 'activo' && cursohaciendaContratacion.usuario == 1 && cursohaciendaContratacion.numeroCurso <= (cantidadCursos + 30003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursohaciendaContratacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursohaciendaContratacion.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursohaciendaContratacion.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursohaciendaContratacion.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- <div v-if="Object.keys(cursos.haciendaContratacion).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(4)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div> -->
            </div>
            <!-- 5 -->
            <div v-if="propt == 5" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Inclusión social</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoinclusionSocial, identificador) in cursos.inclusionSocial" :key="cursoinclusionSocial.id">
                        <div v-if="cursoinclusionSocial.estado == 'activo' && cursoinclusionSocial.usuario == 1 && cursoinclusionSocial.numeroCurso <= (cantidadCursos + 40003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoinclusionSocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoinclusionSocial.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoinclusionSocial.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursoinclusionSocial.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.inclusionSocial).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(5)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 6 -->
            <div v-if="propt == 6" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Salud</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursosalud, identificador) in cursos.salud" :key="cursosalud.id">
                        <div v-if="cursosalud.estado == 'activo' && cursosalud.usuario == 1 && cursosalud.numeroCurso <= (cantidadCursos + 50007)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosalud.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosalud.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosalud.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursosalud.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.salud).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(6)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 7 -->
            <div v-if="propt == 7" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Seguridad vial</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoseguridadVial, identificador) in cursos.seguridadVial" :key="cursoseguridadVial.id">
                        <div v-if="cursoseguridadVial.estado == 'activo' && cursoseguridadVial.usuario == 1 && cursoseguridadVial.numeroCurso <= (cantidadCursos + 60003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadVial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadVial.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadVial.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.seguridadVial).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(7)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 8 -->
            <div v-if="propt == 8" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Seguridad y salud en el trabajo</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoseguridadSaludTrabajo, identificador) in cursos.seguridadSaludTrabajo" :key="cursoseguridadSaludTrabajo.id">
                        <div v-if="cursoseguridadSaludTrabajo.estado == 'activo' && cursoseguridadSaludTrabajo.usuario == 1 && cursoseguridadSaludTrabajo.numeroCurso <= (cantidadCursos + 70003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadSaludTrabajo.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadSaludTrabajo.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadSaludTrabajo.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursoseguridadSaludTrabajo.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- <div v-if="Object.keys(cursos.seguridadSaludTrabajo).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(8)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div> -->
            </div>
            <!-- 9 -->
            <div v-if="propt == 9" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Seminarios</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                        <div v-if="cursoseminarios.estado == 'activo' && cursoseminarios.usuario == 1 && cursoseminarios.numeroCurso <= (cantidadCursos + 80003)" class="accordion-item index-cursos-accordion">
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
                <div v-if="Object.keys(cursos.seminarios).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(9)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 10 -->
            <div v-if="propt == 10" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Social</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursosocial, identificador) in cursos.social" :key="cursosocial.id">
                        <div v-if="cursosocial.estado == 'activo' && cursosocial.usuario == 1 && cursosocial.numeroCurso <= (cantidadCursos + 90006)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosocial.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosocial.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursosocial.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.social).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(10)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
            <!-- 11 -->
            <div v-if="propt == 11" class="d-flex flex-column">
                <div class="mb-3">
                    <h3 class="d-flex justify-content-center">
                        <span class="index-cursos-titulo">Tecnología e innovación</span>
                    </h3>
                </div>
                <div class="d-flex flex-wrap justify-content-center">
                    <div v-for="(cursotecnologiaInnovacion, identificador) in cursos.tecnologiaInnovacion" :key="cursotecnologiaInnovacion.id">
                        <div v-if="cursotecnologiaInnovacion.estado == 'activo' && cursotecnologiaInnovacion.usuario == 1 && cursotecnologiaInnovacion.numeroCurso <= (cantidadCursos + 100003)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursotecnologiaInnovacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursotecnologiaInnovacion.nombre }}</strong>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursotecnologiaInnovacion.contenido }}
                                    </div>
                                    <div class="d-flex justify-content-center">
                                        <a :href="cursotecnologiaInnovacion.link" class="index-cursos-button-inscribete">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-if="Object.keys(cursos.tecnologiaInnovacion).length > 3">
                    <div class="text-center m-2">
                        <button v-on:click="explorar(11)" class="index-cursos-masCursos">VER MÁS CURSOS</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import datos from '../assets/cursos.json'
import CpSubCursos from '../components/CpSubCursos.vue'

export default {
  name: 'CpCiudadano',
  data () {
    return {
      cursos: datos,
      CursosCompletos: 0,
      cantidadCursos: 10000,
      usuario: 1
    }
  },
  components: {
    CpSubCursos
  },
  props: {
    propt: {
      type: Number
    }
  },
  methods: {
    explorar (valor) {
      this.CursosCompletos = valor
    },
    salir () {
      this.CursosCompletos = 0
    }
  }
}
</script>
