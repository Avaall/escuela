<template>
    <div>
      <!-- Header -->
        <div class="index-header-usuario">
            <div class="index-sub-header-usuario">
              <p class="index-header-texto-usuario-1">Alcaldía de Medellín</p>
              <p class="index-header-texto-usuario-2">Escuela Virtual de Aprendizaje</p>
            </div>
        </div>
      <!-- FIN Header -->
      <!-- Navegador o Menu -->
        <div class="index-nav-usuario">
            <div class="container index-nav-container">
                <div class="d-flex">
                  <a href="/" class="index-nav-button-principal">
                    <img src="../assets/img/index-footer-home.png" width="30px" height="25px" class="fluid" alt="">
                    <span>Página principal</span>
                  </a>
                    <span v-on:click="mostrarInicio" class="index-nav-button">Inicio</span>
                    <span v-on:click="mostrarCursos" class="index-nav-button">Cursos</span>
                </div>
                <a href="https://escuelavirtual.medellin.gov.co/login/index.php" target="_blank"
                    class="index-nav-button-ingreso">
                    Ir al Campus
                </a>
            </div>
        </div>
      <!-- FIN Navegador o Menu -->
      <!-- Visualización del contenido según usuario -->
        <div class="container">
            <CpInicio v-if="mostrar_inicio" :mi-variable="sub_id" />
            <CpCursos v-if="mostrar_cursos" :mi-variable="sub_id" />
        </div>
      <!-- FIN Visualización del contenido según usuario -->
      <!-- Footer -->
      <div class="d-flex justify-content-between w-100 home-footer px-5">
            <div class="d-flex home-footer-limit">
                <img src="../assets/img/footer-logo.png" alt="" class="img-fluid home-footer-img">
            </div>
            <div class="home-footer-limit text-center m-auto">
                <div class="d-flex flex-column justify-content-center mx-3">
                    <span>escuelavirtual@medellin.gov.co</span>
                    <span>(604) 385 5555 Ext. 7398 o 7619</span>
                </div>
            </div>
            <div class="home-footer-limit d-flex justify-content-end align-items-center">
            </div>
        </div>
        <!-- FIN Footer -->
    </div>
</template>

<script>
import CpInicio from '../components/CpInicio.vue'
import CpCursos from '../components/CpCursos.vue'

export default {
  data () {
    return {
      mostrar_inicio: true,
      mostrar_cursos: false,
      sub_id: this.miVariable
    }
  },
  props: ['miVariable'],
  components: {
    CpInicio,
    CpCursos
  },
  methods: {
    mostrarInicio () {
      this.mostrar_inicio = true
      this.mostrar_cursos = false
    },
    mostrarCursos () {
      this.mostrar_inicio = false
      this.mostrar_cursos = true
    }
  }
}
</script>
