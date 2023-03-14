<template>
    <div>
        <!-- Buscador y Titulo -->
        <div>
            <h1 class="my-5 d-flex flex-column index-cursos-titulo-general">
                <div class="d-flex justify-content-between align-items-center">
                    <p class="d-flex align-items-center justify-content-center"><strong>Cursos</strong>&nbsp;por categoría</p>
                    <div class="d-flex">
                        <input class="form-control me-2 d-none d-sm-block" id="buscador" type="search" placeholder="Buscar" v-model="buscar" aria-label="Search">
                        <button id="buttonSearch" class="d-block index-cursos-button-search" v-on:click="buscarResponsive">
                            <span>
                                <i class="bi bi-search"></i>
                            </span>
                            <span>Buscar</span>
                        </button>
                    </div>
                </div>
                <div class="index-cursos-sub-linea"></div>
            </h1>
        </div>
        <div v-if="buscar !== ''">
            <div v-if="miVariable == 1" class="d-flex flex-wrap justify-content-center">
                <div v-for="(cursoconvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoconvivenciaCiudadana.id">
                    <div v-if="cursoconvivenciaCiudadana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoconvivenciaCiudadana.requisitos.estado == 'activo' && cursoconvivenciaCiudadana.requisitos.ofertado && cursoconvivenciaCiudadana.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoconvivenciaCiudadana.figure.imagen" :alt="cursoconvivenciaCiudadana.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoconvivenciaCiudadana.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoconvivenciaCiudadana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoconvivenciaCiudadana.contenido }}
                                    </div>
                                    <div v-if="cursoconvivenciaCiudadana.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoconvivenciaCiudadana.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursodiversidadGenero, identificador) in cursos.diversidadGenero" :key="cursodiversidadGenero.id">
                    <div v-if="cursodiversidadGenero.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursodiversidadGenero.requisitos.estado == 'activo' && cursodiversidadGenero.requisitos.ofertado && cursodiversidadGenero.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursodiversidadGenero.figure.imagen" :alt="cursodiversidadGenero.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursodiversidadGenero.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursodiversidadGenero.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursodiversidadGenero.contenido }}
                                    </div>
                                    <div v-if="cursodiversidadGenero.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursodiversidadGenero.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursogestionHumana, identificador) in cursos.gestionHumana" :key="cursogestionHumana.id">
                    <div v-if="cursogestionHumana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursogestionHumana.requisitos.estado == 'activo' && cursogestionHumana.requisitos.ofertado && cursogestionHumana.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursogestionHumana.figure.imagen" :alt="cursogestionHumana.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursogestionHumana.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursogestionHumana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursogestionHumana.contenido }}
                                    </div>
                                    <div v-if="cursogestionHumana.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursogestionHumana.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursohaciendaContratacion, identificador) in cursos.haciendaContratacion" :key="cursohaciendaContratacion.id">
                    <div v-if="cursohaciendaContratacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursohaciendaContratacion.requisitos.estado == 'activo' && cursohaciendaContratacion.requisitos.ofertado && cursohaciendaContratacion.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursohaciendaContratacion.figure.imagen" :alt="cursohaciendaContratacion.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursohaciendaContratacion.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursohaciendaContratacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursohaciendaContratacion.contenido }}
                                    </div>
                                    <div v-if="cursohaciendaContratacion.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursohaciendaContratacion.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoinclusionSocial, identificador) in cursos.inclusionSocial" :key="cursoinclusionSocial.id">
                    <div v-if="cursoinclusionSocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoinclusionSocial.requisitos.estado == 'activo' && cursoinclusionSocial.requisitos.ofertado && cursoinclusionSocial.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoinclusionSocial.figure.imagen" :alt="cursoinclusionSocial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoinclusionSocial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoinclusionSocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoinclusionSocial.contenido }}
                                    </div>
                                    <div v-if="cursoinclusionSocial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoinclusionSocial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursosalud, identificador) in cursos.salud" :key="cursosalud.id">
                    <div v-if="cursosalud.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosalud.requisitos.estado == 'activo' && cursosalud.requisitos.ofertado && cursosalud.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosalud.figure.imagen" :alt="cursosalud.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosalud.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursosalud.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosalud.contenido }}
                                    </div>
                                    <div v-if="cursosalud.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursosalud.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseguridadVial, identificador) in cursos.seguridadVial" :key="cursoseguridadVial.id">
                    <div v-if="cursoseguridadVial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadVial.requisitos.estado == 'activo' && cursoseguridadVial.requisitos.ofertado && cursoseguridadVial.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadVial.figure.imagen" :alt="cursoseguridadVial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadVial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseguridadVial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadVial.contenido }}
                                    </div>
                                    <div v-if="cursoseguridadVial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseguridadVial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoseguridadSaludTrabajo, identificador) in cursos.seguridadcursoseguridadSaludTrabajo" :key="cursoseguridadSaludTrabajo.id">
                    <div v-if="cursoseguridadSaludTrabajo.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadSaludTrabajo.requisitos.estado == 'activo' && cursoseguridadSaludTrabajo.requisitos.ofertado && cursoseguridadSaludTrabajo.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadSaludTrabajo.figure.imagen" :alt="cursoseguridadSaludTrabajo.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadSaludTrabajo.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseguridadSaludTrabajo.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadSaludTrabajo.contenido }}
                                    </div>
                                    <div v-if="cursoseguridadSaludTrabajo.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseguridadSaludTrabajo.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                    <div v-if="cursoseminarios.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseminarios.requisitos.estado == 'activo' && cursoseminarios.requisitos.ofertado && cursoseminarios.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseminarios.figure.imagen" :alt="cursoseminarios.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseminarios.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseminarios.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseminarios.contenido }}
                                    </div>
                                    <div v-if="cursoseminarios.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseminarios.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosocial, identificador) in cursos.social" :key="cursosocial.id">
                    <div v-if="cursosocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosocial.requisitos.estado == 'activo' && cursosocial.requisitos.ofertado && cursosocial.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosocial.figure.imagen" :alt="cursosocial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosocial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursosocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosocial.contenido }}
                                    </div>
                                    <div v-if="cursosocial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursosocial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursotecnologiaInnovacion, identificador) in cursos.tecnologiaInnovacion" :key="cursotecnologiaInnovacion.id">
                    <div v-if="cursotecnologiaInnovacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursotecnologiaInnovacion.requisitos.estado == 'activo' && cursotecnologiaInnovacion.requisitos.ofertado && cursotecnologiaInnovacion.requisitos.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursotecnologiaInnovacion.figure.imagen" :alt="cursotecnologiaInnovacion.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursotecnologiaInnovacion.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursotecnologiaInnovacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursotecnologiaInnovacion.contenido }}
                                    </div>
                                    <div v-if="cursotecnologiaInnovacion.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursotecnologiaInnovacion.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div v-if="miVariable == 2" class="d-flex flex-wrap justify-content-center">
                <div v-for="(cursoconvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoconvivenciaCiudadana.id">
                    <div v-if="cursoconvivenciaCiudadana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoconvivenciaCiudadana.requisitos.estado == 'activo' && cursoconvivenciaCiudadana.requisitos.ofertado && (cursoconvivenciaCiudadana.requisitos.usuario == 1 || cursoconvivenciaCiudadana.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoconvivenciaCiudadana.figure.imagen" :alt="cursoconvivenciaCiudadana.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoconvivenciaCiudadana.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoconvivenciaCiudadana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoconvivenciaCiudadana.contenido }}
                                    </div>
                                    <div v-if="cursoconvivenciaCiudadana.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoconvivenciaCiudadana.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursodiversidadGenero, identificador) in cursos.diversidadGenero" :key="cursodiversidadGenero.id">
                    <div v-if="cursodiversidadGenero.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursodiversidadGenero.requisitos.estado == 'activo' && cursodiversidadGenero.requisitos.ofertado && (cursodiversidadGenero.requisitos.usuario == 1 || cursodiversidadGenero.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursodiversidadGenero.figure.imagen" :alt="cursodiversidadGenero.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursodiversidadGenero.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursodiversidadGenero.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursodiversidadGenero.contenido }}
                                    </div>
                                    <div v-if="cursodiversidadGenero.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursodiversidadGenero.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursogestionHumana, identificador) in cursos.gestionHumana" :key="cursogestionHumana.id">
                    <div v-if="cursogestionHumana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursogestionHumana.requisitos.estado == 'activo' && cursogestionHumana.requisitos.ofertado && (cursogestionHumana.requisitos.usuario == 1 || cursogestionHumana.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursogestionHumana.figure.imagen" :alt="cursogestionHumana.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursogestionHumana.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursogestionHumana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursogestionHumana.contenido }}
                                    </div>
                                    <div v-if="cursogestionHumana.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursogestionHumana.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursohaciendaContratacion, identificador) in cursos.haciendaContratacion" :key="cursohaciendaContratacion.id">
                    <div v-if="cursohaciendaContratacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursohaciendaContratacion.requisitos.estado == 'activo' && cursohaciendaContratacion.requisitos.ofertado && (cursohaciendaContratacion.requisitos.usuario == 1 || cursohaciendaContratacion.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursohaciendaContratacion.figure.imagen" :alt="cursohaciendaContratacion.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursohaciendaContratacion.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursohaciendaContratacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursohaciendaContratacion.contenido }}
                                    </div>
                                    <div v-if="cursohaciendaContratacion.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursohaciendaContratacion.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoinclusionSocial, identificador) in cursos.inclusionSocial" :key="cursoinclusionSocial.id">
                    <div v-if="cursoinclusionSocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoinclusionSocial.requisitos.estado == 'activo' && cursoinclusionSocial.requisitos.ofertado && (cursoinclusionSocial.requisitos.usuario == 1 || cursoinclusionSocial.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoinclusionSocial.figure.imagen" :alt="cursoinclusionSocial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoinclusionSocial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoinclusionSocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoinclusionSocial.contenido }}
                                    </div>
                                    <div v-if="cursoinclusionSocial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoinclusionSocial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursosalud, identificador) in cursos.salud" :key="cursosalud.id">
                    <div v-if="cursosalud.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosalud.requisitos.estado == 'activo' && cursosalud.requisitos.ofertado && (cursosalud.requisitos.usuario == 1 || cursosalud.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosalud.figure.imagen" :alt="cursosalud.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosalud.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursosalud.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosalud.contenido }}
                                    </div>
                                    <div v-if="cursosalud.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursosalud.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseguridadVial, identificador) in cursos.seguridadVial" :key="cursoseguridadVial.id">
                    <div v-if="cursoseguridadVial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadVial.requisitos.estado == 'activo' && cursoseguridadVial.requisitos.ofertado && (cursoseguridadVial.requisitos.usuario == 1 || cursoseguridadVial.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadVial.figure.imagen" :alt="cursoseguridadVial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadVial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseguridadVial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadVial.contenido }}
                                    </div>
                                    <div v-if="cursoseguridadVial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseguridadVial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoseguridadSaludTrabajo, identificador) in cursos.seguridadcursoseguridadSaludTrabajo" :key="cursoseguridadSaludTrabajo.id">
                    <div v-if="cursoseguridadSaludTrabajo.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadSaludTrabajo.requisitos.estado == 'activo' && cursoseguridadSaludTrabajo.requisitos.ofertado && (cursoseguridadSaludTrabajo.requisitos.usuario == 1 || cursoseguridadSaludTrabajo.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadSaludTrabajo.figure.imagen" :alt="cursoseguridadSaludTrabajo.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadSaludTrabajo.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseguridadSaludTrabajo.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadSaludTrabajo.contenido }}
                                    </div>
                                    <div v-if="cursoseguridadSaludTrabajo.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseguridadSaludTrabajo.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="d-none" v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                    <div v-if="cursoseminarios.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseminarios.requisitos.estado == 'activo' && cursoseminarios.requisitos.ofertado && (cursoseminarios.requisitos.usuario == 1 || cursoseminarios.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseminarios.figure.imagen" :alt="cursoseminarios.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseminarios.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursoseminarios.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseminarios.contenido }}
                                    </div>
                                    <div v-if="cursoseminarios.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursoseminarios.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosocial, identificador) in cursos.social" :key="cursosocial.id">
                    <div v-if="cursosocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosocial.requisitos.estado == 'activo' && cursosocial.requisitos.ofertado && (cursosocial.requisitos.usuario == 1 || cursosocial.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosocial.figure.imagen" :alt="cursosocial.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosocial.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursosocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosocial.contenido }}
                                    </div>
                                    <div v-if="cursosocial.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursosocial.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursotecnologiaInnovacion, identificador) in cursos.tecnologiaInnovacion" :key="cursotecnologiaInnovacion.id">
                    <div v-if="cursotecnologiaInnovacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursotecnologiaInnovacion.requisitos.estado == 'activo' && cursotecnologiaInnovacion.requisitos.ofertado && (cursotecnologiaInnovacion.requisitos.usuario == 1 || cursotecnologiaInnovacion.requisitos.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursotecnologiaInnovacion.figure.imagen" :alt="cursotecnologiaInnovacion.figure.alt" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursotecnologiaInnovacion.nombre }}</strong> <br>
                                        <i>Categoría: {{ cursotecnologiaInnovacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursotecnologiaInnovacion.contenido }}
                                    </div>
                                    <div v-if="cursotecnologiaInnovacion.requisitos.botonInscribir == 'si'" class="d-flex justify-content-center">
                                        <a :href="cursotecnologiaInnovacion.requisitos.link" class="index-cursos-button-inscribete" target="_blank">INSCRIBETE</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div v-else>
            <div class="index-cursos-menu">
                <div id="sub-menus" class="d-block h-100 index-cursos-menu-sub">
                    <ul class="index-cursos-menu-ul">
                        <li class="index-cursos-menu-ul-li" v-on:click="number(1)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Convivencia ciudadana
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(2)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Diversidad y género
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(3)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Gestión humana
                        </li>
                        <li id="hacienda" class="d-none index-cursos-menu-ul-li" v-on:click="number(4)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Hacienda y contratación
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(5)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Inclusión social
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(6)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Salud
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(7)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Seguridad vial
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(8)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Seguridad y salud en el trabajo
                        </li>
                        <li class="d-none index-cursos-menu-ul-li" v-on:click="number(9)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Seminarios
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(10)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Social
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(11)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Tecnología e innovación
                        </li>
                    </ul>
                </div>
                <div v-if="miVariable == 1" id="index-visualizacion" class="index-cursos-visualizacion">
                    <div class="div-tema">
                        <label for="">Categoría:</label>
                        <select class="mx-3" v-model="categoria" name="" v-on:change="mover" id="select">
                            <option value="Convivencia ciudadana">Convivencia ciudadana</option>
                            <option value="Seguridad vial">Seguridad vial</option>
                            <option value="Social">Social</option>
                            <option value="Tecnología e innovación">Tecnología e innovación</option>
                        </select>
                    </div>
                    <CpCiudadano id="CpCiudadano" class="w-100 h-100 d-flex align-items-center justify-content-center index-cursos-fondo" :propt="numero" />
                </div>
                <div v-if="miVariable == 2" id="index-visualizacion-2" class="index-cursos-visualizacion">
                    <div class="div-tema">
                        <label for="">Categoría:</label>
                        <select class="mx-3" v-model="categoria" name="" v-on:change="mover" id="select">
                            <option value="Convivencia ciudadana">Convivencia ciudadana</option>
                            <option value="Hacienda y contratación">Hacienda y contratación</option>
                            <option value="Seguridad vial">Seguridad vial</option>
                            <option value="Social">Social</option>
                            <option value="Tecnología e innovación">Tecnología e innovación</option>
                        </select>
                    </div>
                    <CpServidor id="CpServidor" class="w-100 h-100 d-flex align-items-center justify-content-center index-cursos-fondo" :propt="numero" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import datos from '../assets/cursos.json'
import CpCiudadano from '../components/CpCiudadano.vue'
import CpServidor from '../components/CpServidor.vue'

export default {
  data () {
    return {
      cursos: datos,
      numero: 0,
      buscar: '',
      categoria: '',
      ejecutado: false
    }
  },
  name: 'CpCursos',
  props: {
    miVariable: {
      type: Number
    },
    especifico: {
      type: Number
    }
  },
  components: {
    CpCiudadano,
    CpServidor
  },
  mounted () {
    if (this.especifico === 11) {
      this.number(11)
    }
    if (!this.ejecutado) {
      this.ejecutar()
      this.ejecutado = true
    }
  },
  methods: {
    buscarResponsive () {
      const buton = document.getElementById('buttonSearch')
      buton.classList.remove('d-block')
      buton.classList.add('d-none')
      const input = document.getElementById('buscador')
      input.classList.remove('d-none')
      input.classList.add('d-block')
    },
    ejecutar () {
      if (this.miVariable === 2) {
        document.getElementById('hacienda').classList.remove('d-none')
        document.getElementById('hacienda').classList.add('d-block')
      }
    },
    mover () {
      if (this.categoria === 'Convivencia ciudadana') {
        this.number(1)
      }
      if (this.categoria === 'Diversidad y género') {
        this.number(2)
      }
      if (this.categoria === 'Gestión humana') {
        this.number(3)
      }
      if (this.categoria === 'Hacienda y contratación') {
        this.number(4)
      }
      if (this.categoria === 'Inclusión social') {
        this.number(5)
      }
      if (this.categoria === 'Salud') {
        this.number(6)
      }
      if (this.categoria === 'Seguridad vial') {
        this.number(7)
      }
      if (this.categoria === 'Seguridad y salud en el trabajo"') {
        this.number(8)
      }
      if (this.categoria === 'Seminarios') {
        this.number(9)
      }
      if (this.categoria === 'Social') {
        this.number(10)
      }
      if (this.categoria === 'Tecnología e innovación') {
        this.number(11)
      }
    },
    number (valor) {
      if (this.miVariable === 1) {
        document.getElementById('CpCiudadano').style.background = 'none'
      }
      if (this.miVariable === 2) {
        document.getElementById('CpServidor').style.background = 'none'
      }
      if (window.screen.width < 769) {
        if (this.miVariable === 1) {
          const a = document.getElementById('sub-menus')
          a.classList.remove('index-cursos-menu-sub')
          a.classList.remove('d-block')
          a.classList.add('d-none')
          const b = document.getElementById('index-visualizacion')
          b.classList.add('d-block')
        }
        if (this.miVariable === 2) {
          const a = document.getElementById('sub-menus')
          a.classList.remove('index-cursos-menu-sub')
          a.classList.remove('d-block')
          a.classList.add('d-none')
          const b = document.getElementById('index-visualizacion-2')
          b.classList.add('d-block')
        }
      }
      this.valorCurso = 0
      this.numero = valor
      const li = document.querySelectorAll('.index-cursos-menu-ul-li')
      for (let i = 0; i < li.length; i++) {
        if (li[valor - 1] === li[i]) {
          li[i].classList.add('index-cursos-menu-ul-li-activado')
        }
        if (li[i] !== li[valor - 1]) {
          li[i].classList.remove('index-cursos-menu-ul-li-activado')
        }
      }
    }
  }
}
</script>
