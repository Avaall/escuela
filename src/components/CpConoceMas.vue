<template>
    <div id="CpInicio">
        <!-- Primera sección sobre la escuela -->
        <div class="d-flex align-items-center mt-5">
            <div class="w-50 index-inicio-info">
                <h1 class="index-inicio-titulo">¿Qué es la Escuela Virtual de Aprendizaje?</h1>
                <span class="text-inicio">
                    Es una de las estrategias de formación, capacitación y entrenamiento de
                    la Alcaldía de Medellín para fortalecer las competencias y capacidades de
                    los servidores públicos y de la ciudadanía, mediante programas de aprendizaje
                    con énfasis en diferentes temáticas.
                </span>
            </div>
            <div class="w-50">
                <img src="../assets/img/index-1.jpg" alt="" class="img-fluid">
            </div>
        </div>
        <!-- FIN Primera sección sobre la escuela -->
        <!-- Segunda sección sobre la escuela -->
        <div class="d-flex align-items-center my-5">
            <div class="w-50">
                <img src="../assets/img/index-inicio-logo.png" alt="" class="img-fluid index-inicio-logo">
            </div>
            <div class="w-50">
                <div class="accordion" id="accordionExample">
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingOne">
                            <button class="accordion-button index-inicio-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                                <span>¿Por qué la Alcaldía de Medellín cuenta con una Escuela Virtual de Aprendizaje?</span>
                            </button>
                        </h2>
                        <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                <span>
                                    Para garantizar la correcta prestación de servicios a la ciudadanía, la Alcaldía
                                    de Medellín es responsable de la gestión integral del talento humano, es decir,
                                    de los servidores públicos. Así nació la necesidad de contar con una estrategia
                                    de formación y capacitación interna, sin embargo, dado que las temáticas de los
                                    cursos resultaron de interés general, se decidió abrir la oferta a la ciudadanía.
                                </span>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingTwo">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
                                <span>Misión</span>
                            </button>
                        </h2>
                        <div id="collapseTwo" class="accordion-collapse collapse" aria-labelledby="headingTwo" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                <span>
                                    Facilitar los procesos de enseñanza y aprendizaje desde el SER (formación),
                                    el HACER (entrenamiento) y el SABER (capacitación).
                                </span>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingThree">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
                                <span>¿Cuánto programas de aprendizaje tiene la plataforma?</span>
                            </button>
                        </h2>
                        <div id="collapseThree" class="accordion-collapse collapse" aria-labelledby="headingThree" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                Actualmente hay 64 programas de aprendizaje, 56 cursos y 8 diplomados.
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingFour">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseFour" aria-expanded="false" aria-controls="collapseFour">
                                <span>Otros datos sobre la Escuela Virtual de Aprendizaje</span>
                            </button>
                        </h2>
                        <div id="collapseFour" class="accordion-collapse collapse" aria-labelledby="headingFour" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                A partir de mayo se reactivará en la plataforma la metodología PREA
                                para la prevención del embarazo adolescente, construida por un grupo
                                de expertos en tecnología e innovación e implementada a través de objetos
                                virtuales de aprendizaje, tales como cartillas, videojuegos, podcasts,
                                cuentos y material educativo. <br><br>

                                Se encuentran en funcionamiento los simulacros de pruebas ICFES para los
                                alumnos de grado 11 y saber pro para los alumnos de 9 y 10 de todas las
                                instituciones públicas. Durante la pandemia, la plataforma tomó más fuerza,
                                gracias a la divulgación y promoción del aprendizaje ofrecido por las dependencias.
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- FIN Segunda sección sobre la escuela -->
    </div>
</template>

<script>
export default {
  name: 'CpInicio',
  props: ['miVariable']
}
</script>
