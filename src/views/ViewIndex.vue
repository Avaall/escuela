<template>
    <div id="Modals">
        <!-- Header -->
        <div class="home-header">
            <div class="home-header-bg align-items-center d-flex">
                <div class="d-flex w-100 justify-content-between align-items-center">
                    <div class="mx-5">
                        <p class="home-header-texto-1 m-0">Alcaldía de Medellín</p>
                        <p class="home-header-texto-2 m-0">Escuela Virtual de Aprendizaje</p>
                    </div>
                    <div class="cursor" v-on:click="AbrirMenu">
                        <img src="../assets/img/boton-ingreso.png" alt="" width="220px" class="mx-5">
                    </div>
                </div>
            </div>
        </div>
        <!-- FIN Header -->
        <!-- Body carousel -->
        <div id="carousel" class="carousel slide home-carousel" data-bs-ride="true">
            <div class="carousel-indicators">
                <button type="button" data-bs-target="#carousel" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
                <button type="button" data-bs-target="#carousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
            </div>
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img src="../assets/img/carousel-1.png" class="d-block h-100 img-carousel" alt="...">
                    <div class="carousel-caption d-flex justify-content-end h-100 align-items-center home-carousel-animation">
                        <img src="../assets/img/carousel-logo-escuela.png" alt="" width="400px" class="info-caption">
                    </div>
                </div>
                <div class="carousel-item">
                    <img src="../assets/img/carousel-2.png" class="d-block h-100 img-carousel" alt="...">
                    <div class="carousel-caption d-flex flex-column justify-content-center h-100 align-items-center">
                        <div class="home-carousel-text home-carousel-animation">
                            <center class="info-caption"><span>La <strong>Escuela Virtual de Aprendizaje</strong><br>es un espacio para compartir,<br> explorar y descubrir conocimientos</span></center>
                        </div>
                    </div>
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carousel" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carousel" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </button>
        </div>
        <!-- FIN Body carousel -->
        <!-- Información adicional para el Conoce Más -->
        <section id="home-section" class="home-section">
            <div class="home-informacion">
                <div class="home-informacion-button" v-on:click="MostrarInfoButton(0)">
                    <img src="../assets/img/modal-icon-1.png" alt="" class="mt-2 home-icon-informacion">
                    <p class="text-center mx-2 home-valor-texto-titulo">¿Qué es la Escuela Virtual de Aprendizaje?</p>
                </div>
                <div class="home-informacion-body">
                    Es una de las estrategias de formación, capacitación y entrenamiento de
                    la Alcaldía de Medellín para fortalecer las competencias laborales de los
                    servidores públicos, mediante programas de aprendizaje con énfasis en
                    actualización permanente del fortalecimiento de la cultura organizacional
                    y la ética de los servicios ofrecidos a la ciudadanía.
                    <div>
                        <button v-on:click="cerrar(0)">Cerrar</button>
                    </div>
                </div>
                <div class="home-informacion-button" v-on:click="MostrarInfoButton(1)">
                    <img src="../assets/img/modal-icon-2.png" alt="" class="mt-2 home-icon-informacion">
                    <p class="text-center mx-2 home-valor-texto-titulo">¿Cuándo nace? <br> &nbsp;</p>
                </div>
                <div class="home-informacion-body">
                    Se crea desde la Secretaría de Gestión Humana y Servicio a la Ciudadanía.
                    Se ve la necesidad de capacitar a los servidores en cuanto a ética y
                    cultura organizacional, ya que tiene como responsabilidad la estructura
                    organizacional, La gestión integral del talento humano, La gestión de la
                    información, La tecnología para el mejoramiento continuo de la prestación
                    de servicios.
                    <div>
                        <button v-on:click="cerrar(1)">Cerrar</button>
                    </div>
                </div>
                <div class="home-informacion-button" v-on:click="MostrarInfoButton(2)">
                    <img src="../assets/img/modal-icon-3.png" alt="" class="mt-2 home-icon-informacion">
                    <p class="text-center mx-2 home-valor-texto-titulo">Misión <br> &nbsp;</p>
                </div>
                <div class="home-informacion-body">
                    Su misión se cimienta en tres aspectos: el SER (su formación),
                    el HACER (su entrenamiento) y el SABER (su capacitación).
                    <div>
                        <button v-on:click="cerrar(2)">Cerrar</button>
                    </div>
                </div>
                <div class="home-informacion-button" v-on:click="MostrarInfoButton(3)">
                    <img src="../assets/img/modal-icon-4.png" alt="" class="mt-2 home-icon-informacion">
                    <p class="text-center mx-2 home-valor-texto-titulo">Programas <br> &nbsp;</p>
                </div>
                <div class="home-informacion-body">
                    La plataforma cuenta con 13 secretarías Actualmente
                    hay 64 programas de aprendizaje, 56 cursos y 8 diplomados.
                    <div>
                        <button v-on:click="cerrar(3)">Cerrar</button>
                    </div>
                </div>
                <div class="home-informacion-button" v-on:click="MostrarInfoButton(4)">
                    <img src="../assets/img/modal-icon-5.png" alt="" class="mt-2 home-icon-informacion">
                    <p class="text-center mx-2 home-valor-texto-titulo">Otros datos <br> &nbsp;</p>
                </div>
                <div class="home-informacion-body">
                    A partir de mayo se reactivará en la plataforma la metodología
                    PREA para la prevención del embarazo adolescente, construida por
                    un grupo de expertos en tecnología e innovación e implementada a
                    través de objetos virtuales de aprendizaje, tales como cartillas,
                    videojuegos, podcasts, cuentos y material educativo.

                    Se encuentran en funcionamiento los simulacros de pruebas ICFES
                    para los alumnos de grado 11 y saber pro para los alumnos de 9 y
                    10 de todas las instituciones públicas. Durante la pandemia, la
                    plataforma tomó más fuerza, gracias a la divulgación y promoción
                    del aprendizaje ofrecido por las dependencias.el contenido de los cursos, la temática, metodología y duración
                    del mismo.
                    <div>
                        <button v-on:click="cerrar(4)">Cerrar</button>
                    </div>
                </div>
            </div>
        </section>
        <!-- FIN Información adicional para el Conoce Más -->
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
export default {
  methods: {
    AbrirMenu () {
      document.getElementById('usuario-ingresar').style.top = '0px'
    },
    MostrarInfoButton (i) {
      const informacion = document.querySelectorAll('.home-informacion-body')
      const button = document.querySelectorAll('.home-informacion-button')
      for (let x = 0; x <= informacion.length; x++) {
        if (x === i) {
          informacion[i].style.animation = 'home-informacion-aparecer forwards 1s'
        }
        if (x !== i) {
          button[x].classList.add('d-none')
        }
      }
    },
    cerrar (i) {
      const button = document.querySelectorAll('.home-informacion-button')
      const informacion = document.querySelectorAll('.home-informacion-body')
      for (let x = 0; x <= informacion.length; x++) {
        if (x === i) {
          informacion[i].style.animation = ''
        }
        if (x !== i) {
          button[x].classList.remove('d-none')
        }
      }
    }
  },
  name: 'IndexIncio'
}
</script>
