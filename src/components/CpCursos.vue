<template>
    <div>
        <!-- Buscador y Titulo -->
        <div>
            <h1 class="my-5 d-flex flex-column index-cursos-titulo-general">
                <div class="d-flex justify-content-between">
                    <strong>Cursos por categoría</strong>
                    <div class="d-flex">
                        <input class="form-control me-2" id="buscador" type="search" placeholder="Buscar" v-model="buscar" aria-label="Search">
                        <button class="index-cursos-button-search">Buscar</button>
                    </div>
                </div>
                <div class="index-cursos-sub-linea"></div>
            </h1>
        </div>
        <div v-if="buscar !== ''">
            <div v-if="miVariable == 1" class="d-flex flex-wrap justify-content-center">
                <div v-for="(cursoconvivenciaCiudadana, identificador) in cursos.convivenciaCiudadana" :key="cursoconvivenciaCiudadana.id">
                    <div v-if="cursoconvivenciaCiudadana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoconvivenciaCiudadana.estado == 'activo' && cursoconvivenciaCiudadana.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoconvivenciaCiudadana.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoconvivenciaCiudadana.nombre }}</strong> <br>
                                        <i>{{ cursoconvivenciaCiudadana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoconvivenciaCiudadana.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursodiversidadGenero, identificador) in cursos.diversidadGenero" :key="cursodiversidadGenero.id">
                    <div v-if="cursodiversidadGenero.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursodiversidadGenero.estado == 'activo' && cursodiversidadGenero.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursodiversidadGenero.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursodiversidadGenero.nombre }}</strong> <br>
                                        <i>{{ cursodiversidadGenero.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursodiversidadGenero.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursogestionHumana, identificador) in cursos.gestionHumana" :key="cursogestionHumana.id">
                    <div v-if="cursogestionHumana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursogestionHumana.estado == 'activo' && cursogestionHumana.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursogestionHumana.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursogestionHumana.nombre }}</strong> <br>
                                        <i>{{ cursogestionHumana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursogestionHumana.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursohaciendaContratacion, identificador) in cursos.haciendaContratacion" :key="cursohaciendaContratacion.id">
                    <div v-if="cursohaciendaContratacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursohaciendaContratacion.estado == 'activo' && cursohaciendaContratacion.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursohaciendaContratacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursohaciendaContratacion.nombre }}</strong> <br>
                                        <i>{{ cursohaciendaContratacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursohaciendaContratacion.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoinclusionSocial, identificador) in cursos.inclusionSocial" :key="cursoinclusionSocial.id">
                    <div v-if="cursoinclusionSocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoinclusionSocial.estado == 'activo' && cursoinclusionSocial.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoinclusionSocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoinclusionSocial.nombre }}</strong> <br>
                                        <i>{{ cursoinclusionSocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoinclusionSocial.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosalud, identificador) in cursos.salud" :key="cursosalud.id">
                    <div v-if="cursosalud.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosalud.estado == 'activo' && cursosalud.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosalud.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosalud.nombre }}</strong> <br>
                                        <i>{{ cursosalud.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosalud.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseguridadVial, identificador) in cursos.seguridadVial" :key="cursoseguridadVial.id">
                    <div v-if="cursoseguridadVial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadVial.estado == 'activo' && cursoseguridadVial.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadVial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadVial.nombre }}</strong> <br>
                                        <i>{{ cursoseguridadVial.categoria }}</i> <br>
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
                <div v-for="(cursoseguridadSaludTrabajo, identificador) in cursos.seguridadcursoseguridadSaludTrabajo" :key="cursoseguridadSaludTrabajo.id">
                    <div v-if="cursoseguridadSaludTrabajo.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadSaludTrabajo.estado == 'activo' && cursoseguridadSaludTrabajo.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadSaludTrabajo.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadSaludTrabajo.nombre }}</strong> <br>
                                        <i>{{ cursoseguridadSaludTrabajo.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadSaludTrabajo.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                    <div v-if="cursoseminarios.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseminarios.estado == 'activo' && cursoseminarios.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseminarios.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseminarios.nombre }}</strong> <br>
                                        <i>{{ cursoseminarios.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseminarios.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosocial, identificador) in cursos.social" :key="cursosocial.id">
                    <div v-if="cursosocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosocial.estado == 'activo' && cursosocial.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosocial.nombre }}</strong> <br>
                                        <i>{{ cursosocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosocial.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursotecnologiaInnovacion, identificador) in cursos.tecnologiaInnovacion" :key="cursotecnologiaInnovacion.id">
                    <div v-if="cursotecnologiaInnovacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursotecnologiaInnovacion.estado == 'activo' && cursotecnologiaInnovacion.usuario == 1" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursotecnologiaInnovacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursotecnologiaInnovacion.nombre }}</strong> <br>
                                        <i>{{ cursotecnologiaInnovacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursotecnologiaInnovacion.contenido }}
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
                        <div v-if="cursoconvivenciaCiudadana.estado == 'activo' && (cursoconvivenciaCiudadana.usuario == 1 || cursoconvivenciaCiudadana.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoconvivenciaCiudadana.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoconvivenciaCiudadana.nombre }}</strong> <br>
                                        <i>{{ cursoconvivenciaCiudadana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoconvivenciaCiudadana.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursodiversidadGenero, identificador) in cursos.diversidadGenero" :key="cursodiversidadGenero.id">
                    <div v-if="cursodiversidadGenero.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursodiversidadGenero.estado == 'activo' && (cursodiversidadGenero.usuario == 1 || cursodiversidadGenero.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursodiversidadGenero.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursodiversidadGenero.nombre }}</strong> <br>
                                        <i>{{ cursodiversidadGenero.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursodiversidadGenero.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursogestionHumana, identificador) in cursos.gestionHumana" :key="cursogestionHumana.id">
                    <div v-if="cursogestionHumana.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursogestionHumana.estado == 'activo' && (cursogestionHumana.usuario == 1 || cursogestionHumana.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursogestionHumana.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursogestionHumana.nombre }}</strong> <br>
                                        <i>{{ cursogestionHumana.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursogestionHumana.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursohaciendaContratacion, identificador) in cursos.haciendaContratacion" :key="cursohaciendaContratacion.id">
                    <div v-if="cursohaciendaContratacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursohaciendaContratacion.estado == 'activo' && (cursohaciendaContratacion.usuario == 1 || cursohaciendaContratacion.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursohaciendaContratacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursohaciendaContratacion.nombre }}</strong> <br>
                                        <i>{{ cursohaciendaContratacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursohaciendaContratacion.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoinclusionSocial, identificador) in cursos.inclusionSocial" :key="cursoinclusionSocial.id">
                    <div v-if="cursoinclusionSocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoinclusionSocial.estado == 'activo' && (cursoinclusionSocial.usuario == 1 || cursoinclusionSocial.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoinclusionSocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoinclusionSocial.nombre }}</strong> <br>
                                        <i>{{ cursoinclusionSocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoinclusionSocial.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosalud, identificador) in cursos.salud" :key="cursosalud.id">
                    <div v-if="cursosalud.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosalud.estado == 'activo' && (cursosalud.usuario == 1 || cursosalud.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosalud.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosalud.nombre }}</strong> <br>
                                        <i>{{ cursosalud.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosalud.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseguridadVial, identificador) in cursos.seguridadVial" :key="cursoseguridadVial.id">
                    <div v-if="cursoseguridadVial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadVial.estado == 'activo' && (cursoseguridadVial.usuario == 1 || cursoseguridadVial.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadVial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadVial.nombre }}</strong> <br>
                                        <i>{{ cursoseguridadVial.categoria }}</i> <br>
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
                <div v-for="(cursoseguridadSaludTrabajo, identificador) in cursos.seguridadcursoseguridadSaludTrabajo" :key="cursoseguridadSaludTrabajo.id">
                    <div v-if="cursoseguridadSaludTrabajo.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseguridadSaludTrabajo.estado == 'activo' && (cursoseguridadSaludTrabajo.usuario == 1 || cursoseguridadSaludTrabajo.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseguridadSaludTrabajo.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseguridadSaludTrabajo.nombre }}</strong> <br>
                                        <i>{{ cursoseguridadSaludTrabajo.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseguridadSaludTrabajo.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursoseminarios, identificador) in cursos.seminarios" :key="cursoseminarios.id">
                    <div v-if="cursoseminarios.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursoseminarios.estado == 'activo' && (cursoseminarios.usuario == 1 || cursoseminarios.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursoseminarios.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursoseminarios.nombre }}</strong> <br>
                                        <i>{{ cursoseminarios.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursoseminarios.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursosocial, identificador) in cursos.social" :key="cursosocial.id">
                    <div v-if="cursosocial.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursosocial.estado == 'activo' && (cursosocial.usuario == 1 || cursosocial.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursosocial.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursosocial.nombre }}</strong> <br>
                                        <i>{{ cursosocial.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursosocial.contenido }}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div v-for="(cursotecnologiaInnovacion, identificador) in cursos.tecnologiaInnovacion" :key="cursotecnologiaInnovacion.id">
                    <div v-if="cursotecnologiaInnovacion.nombre.trim().toLowerCase().indexOf(buscar.toLowerCase()) !== -1">
                        <div v-if="cursotecnologiaInnovacion.estado == 'activo' && (cursotecnologiaInnovacion.usuario == 1 || cursotecnologiaInnovacion.usuario == 2)" class="accordion-item index-cursos-accordion">
                            <h2 class="accordion-header" id="acordion1">
                                <button class="index-cursos-accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="'#'+identificador" aria-expanded="false" :aria-controls="identificador">
                                    <img :src="cursotecnologiaInnovacion.imagen" alt="foto" class="rounded" width="300px">
                                    <p class="index-cursos-titulo-accordion">
                                        <strong>{{ cursotecnologiaInnovacion.nombre }}</strong> <br>
                                        <i>{{ cursotecnologiaInnovacion.categoria }}</i> <br>
                                    </p>
                                    <span>Conoce Más...</span>
                                </button>
                            </h2>
                            <div :id="identificador" class="collapse" aria-labelledby="acordion1" data-bs-parent="#home-accordion">
                                <div class="index-cursos-cuerpo-accordion">
                                    <div class="d-flex align-items-center">
                                        {{ cursotecnologiaInnovacion.contenido }}
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
                <div class="h-100 index-cursos-menu-sub">
                    <ul class="index-cursos-menu-ul">
                        <li class="index-cursos-menu-ul-li" v-on:click="number(1)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Convivencia ciudadana
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(2)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Diversidad y género
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(3)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Gestión humana
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(4)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Hacienda y contratación
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(5)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Inclusión social
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(6)">
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
                        <li class="index-cursos-menu-ul-li" v-on:click="number(8)">
                            <span class="material-symbols-outlined mx-2">
                                arrow_circle_right
                            </span>
                            Seguridad y salud en el trabajo
                        </li>
                        <li class="index-cursos-menu-ul-li" v-on:click="number(9)">
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
                <div v-if="miVariable == 1" class="index-cursos-visualizacion">
                    <CpCiudadano class="w-100 h-100 d-flex align-items-center justify-content-center" ref="hijo" :propt="numero" />
                </div>
                <div v-if="miVariable == 2" class="index-cursos-visualizacion">
                    <CpServidor class="w-100 h-100 d-flex align-items-center justify-content-center" ref="hijo" :propt="numero" />
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
      buscar: ''
    }
  },
  name: 'CpCursos',
  props: ['miVariable'],
  components: {
    CpCiudadano,
    CpServidor
  },
  methods: {
    number (valor) {
      this.$refs.hijo.salir()
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
