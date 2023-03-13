<template>
    <div id="app">
      <!-- Home ingreso que desciende -->
        <div class="position-fixed usuario-ingresar" id="usuario-ingresar" v-on:click="CerrarMenu">
            <div class="d-block">
                <span class="usuario-close">X</span>
                <h1 class="text-center mb-5 usuario-texto-titulo">¿A qué perfil perteneces?</h1>
                <div class="d-flex flex-row">
                    <div v-on:click="cambiarValor(1)" class="d-flex flex-column align-items-center mx-2 mx-md-5 cursor active-img-logo">
                        <img src="./assets/img/usuario-ciudadano.png" alt="" height="215px" class="usuario-icon">
                        <span class="usuarios-texto">Ciudadanía</span>
                    </div>
                    <div v-on:click="cambiarValor(2)" class="d-flex flex-column align-items-center mx-2 mx-md-5 cursor">
                        <img src="./assets/img/usuario-servidor.png" alt="" height="215px" class="usuario-icon">
                        <span class="usuarios-texto">Servidores</span>
                    </div>
                </div>
                <div class="usuario-texto-medellin">
                    <h5>
                      <center class="font">
                        Los cursos y diplomados ofertados en esta plataforma, van dirigidos <br>
                        exclusivamente a las personas que residan en la ciudad de Medellín
                      </center>
                    </h5>
                </div>
            </div>
        </div>
      <!-- FIN Home ingreso que desciende -->
      <!-- Visualización de la pantalla completa -->
        <section v-if="valor" id="indexUsuario">
            <IndexUsuario :mi-variable="nuevoID" />
        </section>
        <section v-else class="d-block" id="Index">
            <Index />
        </section>
      <!-- FIN Visualización de la pantalla completa -->
    </div>
</template>

<script>
import Index from './views/ViewIndex.vue'
import IndexUsuario from './views/ViewIndexUsuario.vue'

export default {
  data () {
    return {
      valor: false,
      nuevoID: 0
    }
  },
  name: 'App',
  components: {
    Index,
    IndexUsuario
  },
  methods: {
    CerrarMenu () {
      document.getElementById('usuario-ingresar').style.top = '-150vh'
    },
    cambiarValor (x) {
      if (x === 1) {
        this.valor = true
        this.nuevoID = 1
      }
      if (x === 2) {
        this.valor = true
        this.nuevoID = 2
      }
    }
  }
}
</script>
