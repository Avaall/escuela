<template>
    <div id="CpInicio">
        <!-- Primera sección sobre la escuela -->
        <div class="d-flex align-items-center mt-5">
            <div class="w-50 index-inicio-info">
                <h1 class="index-inicio-titulo">¿Qué es la Escuela Virtual de Aprendizaje?</h1>
                <span class="text-inicio">
                    Es una de las estrategias de formación, capacitación y entrenamiento de
                    la Alcaldía de Medellín para fortalecer las competencias laborales de los
                    servidores públicos, mediante programas de aprendizaje con énfasis en
                    actualización permanente del fortalecimiento de la cultura organizacional
                    y la ética de los servicios ofrecidos a la ciudadanía. <br><br>

                    También cuenta con capacitaciones abiertas para la ciudadanía con énfasis
                    en temas para el desarrollo de las empresas, formación humana y laboral,
                    convivencia ciudadana, entre otros. <br><br>

                    La formación es dictada en la plataforma virtual
                    <a href="https://escuelavirtual.medellin.gov.co" target="_blank">https://escuelavirtual.medellin.gov.co</a>
                    ofrecidas por instituciones educativas públicas como el Sena, el Pascual
                    Bravo, el ITM… o por las diferentes dependencias de la Alcaldía. El oferente
                    se encarga del contenido de los cursos, la temática, metodología y duración
                    del mismo.
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
                                <span>¿Cuándo nace la Escuela Virtual de Aprendizaje de la Alcaldía de Medellín?</span>
                            </button>
                        </h2>
                        <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                <span>
                                    Se crea desde la Secretaría de Gestión Humana y Servicio a la Ciudadanía.
                                    Se ve la necesidad de capacitar a los servidores en cuanto a ética y cultura
                                    organizacional, ya que tiene como responsabilidad la estructura organizacional,
                                    La gestión integral del talento humano, La gestión de la información, La
                                    tecnología para el mejoramiento continuo de la prestación de servicios.
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
                                    Su misión se cimienta en tres aspectos: el SER (su formación),
                                    el HACER (su entrenamiento) y el SABER (su capacitación).
                                </span>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingThree">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
                                <span>¿Cuántos son los programas de aprendizaje activos en la plataforma?</span>
                            </button>
                        </h2>
                        <div id="collapseThree" class="accordion-collapse collapse" aria-labelledby="headingThree" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                La plataforma cuenta con 13 secretarías Actualmente hay 64 programas
                                de aprendizaje, 56 cursos y 8 diplomados.
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header" id="headingFour">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseFour" aria-expanded="false" aria-controls="collapseFour">
                                <span>Otros datos sobre la escuela virtual de aprendizaje</span>
                            </button>
                        </h2>
                        <div id="collapseFour" class="accordion-collapse collapse" aria-labelledby="headingFour" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                A partir de mayo se reactivará en la plataforma la metodología PREA
                                para la prevención del embarazo adolescente, construida por un grupo
                                de expertos en tecnología e innovación e implementada a través de
                                objetos virtuales de aprendizaje, tales como cartillas, videojuegos,
                                podcasts, cuentos y material educativo. <br><br>

                                Se encuentran en funcionamiento los simulacros de pruebas ICFES para
                                los alumnos de grado 11 y saber pro para los alumnos de 9 y 10 de todas
                                las instituciones públicas. Durante la pandemia, la plataforma tomó más
                                fuerza, gracias a la divulgación y promoción del aprendizaje ofrecido
                                por las dependencias.
                            </div>
                        </div>
                    </div>
                    <div v-if="miVariable == 2" class="accordion-item">
                        <h2 class="accordion-header" id="headingFive">
                            <button class="accordion-button index-inicio-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseFive" aria-expanded="false" aria-controls="collapseFive">
                                <span>¿Quién maneja la EFIAM?</span>
                            </button>
                        </h2>
                        <div id="collapseFive" class="accordion-collapse collapse" aria-labelledby="headingFive" data-bs-parent="#accordionExample">
                            <div class="accordion-body texto-accordion">
                                Secretaría de Gestión humana: Revisión de los contenidos, desarrollo de
                                los currículos, diseño Institucional, formación y capacitación. <br><br>

                                Secretaría de innovación digital: Apropiación, soporte técnico,
                                fortalecimiento de la plataforma y por ser transversal a varias secretarías,
                                la gobernanza de la plataforma.
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
