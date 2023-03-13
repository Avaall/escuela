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
                <div class="d-flex w-50">
                    <a href="/" class="index-nav-button-principal">
                      <img src="../assets/img/index-footer-home.png" width="30px" height="25px" class="fluid" alt="">
                      <span>Página principal</span>
                    </a>
                    <span v-on:click="mostrarCursos" class="index-nav-button">Cursos</span>
                    <span v-on:click="mostrarConoce" class="index-nav-button">Conócenos más</span>
                </div>
                <a href="https://escuelavirtual.medellin.gov.co/login/index.php" target="_blank"
                    class="index-nav-button-ingreso">
                    Ir al Campus
                </a>
            </div>
            <div class="index-nav-container-responsive">
                <div class="index-nav-responsive">
                    <i class="bi bi-list"></i>
                </div>
                <a href="https://escuelavirtual.medellin.gov.co/login/index.php" target="_blank"
                    class="index-nav-button-ingreso">
                    Ir al Campus
                </a>
            </div>
        </div>
      <!-- FIN Navegador o Menu -->
      <!-- Visualización del contenido según usuario -->
        <div class="container container-b">
            <CpCursos v-if="mostrar_cursos" :especifico="sub_adicion" :miVariable="sub_id" />
            <CpConoceMas v-if="mostrar_conoce" :mi-variable="sub_id" />
        </div>
      <!-- FIN Visualización del contenido según usuario -->
      <!-- Footer -->
      <div class="d-flex justify-content-between w-100 home-footer px-0 px-md-5">
        <div class="d-flex home-footer-limit align-items-center">
        </div>
        <div class="home-footer-limit text-center m-auto">
            <div class="d-flex flex-column justify-content-center mx-3">
                <span>escuelavirtual@medellin.gov.co</span>
                <span>(604) 385 5555 Ext. 7398 o 7619</span>
            </div>
        </div>
        <div class="d-flex home-footer-limit">
            <div class="d-flex align-items-center home-footer-limit-2">
                <img src="../assets/img/footer-logo-sid.png" alt="" width="90px" class="mx-5 home-footer-img-sid">
                <img src="../assets/img/footer-logo.png" alt="" width="200px" class="img-fluid home-footer-img">
            </div>
        </div>
    </div>
        <!-- FIN Footer -->
    </div>
</template>

<script>
import CpConoceMas from '../components/CpConoceMas.vue'
import CpCursos from '../components/CpCursos.vue'

export default {
  data () {
    return {
      mostrar_cursos: true,
      mostrar_conoce: false,
      sub_id: this.miVariable,
      sub_adicion: this.adicional
    }
  },
  props: {
    miVariable: {
      type: Number
    },
    adicional: {
      type: Number
    }
  },
  components: {
    CpConoceMas,
    CpCursos
  },
  methods: {
    mostrarCursos () {
      this.mostrar_cursos = true
      this.mostrar_conoce = false
    },
    mostrarConoce () {
      this.mostrar_cursos = false
      this.mostrar_conoce = true
    }
  }
}
</script>
