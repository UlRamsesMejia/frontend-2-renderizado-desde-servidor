<template>
  <div>
    <b-carousel
      :interval="4000"
      controls
      indicators
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <b-carousel-slide img-src="../assets/img/banner-1.jpg" alt=""></b-carousel-slide>
      <b-carousel-slide img-src="../assets/img/banner-2.jpg" alt=""></b-carousel-slide>
      <b-carousel-slide img-src="../assets/img/banner-3.jpg" alt=""></b-carousel-slide>
      <b-carousel-slide img-src="../assets/img/banner-4.jpg" alt=""></b-carousel-slide>
      <b-carousel-slide img-src="../assets/img/banner-5.jpg" alt=""></b-carousel-slide>
    </b-carousel>
    <div id="servicios" class="container mt-3 pb-3">
      <h2 class="text-center mb-3">
        Servicios
        <font-awesome-icon icon="plus-circle" class="text-success cursor-pointer"
          style="font-size: 1.5rem;" @click="nuevoServicio = {}" v-b-modal.agregarServicio/>
      </h2>
      <div class="row justify-content-center">
        <div v-for="(servicio, i) in servicios" v-bind:key="servicio.id"
          class="col-12 col-md-6 col-lg-4 cursor-pointer" @click="detallesServicio = servicio">
          <div class="text-center">
            <div v-b-modal.detallesServicio>
              <h3>{{ servicio.titulo }}</h3>
              <p>{{ servicio.parrafo }}</p>
            </div>
            <font-awesome-icon :icon="['fas', 'edit']" class="text-primary mx-2" 
              style="font-size: 1.5rem;" v-b-modal.agregarServicio
                @click="nuevoServicio = JSON.parse(JSON.stringify(servicio))"/>
            <font-awesome-icon :icon="['fas', 'times-circle']" class="text-danger mx-2" 
              style="font-size: 1.5rem;" @click="eliminarServicio(i)" />
          </div>
        </div>
      </div>
    </div>
    <div id="nosotros">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <h3 class="text-center">Nuestra Historia</h3>
            <p>
              Con la promulgación del Decreto Nº 1.701 de fecha 7 de abril de 2015,4​ a través del cual se creó el Ministerio del Poder Popular para Ecosocialismo y Aguas, se emprendió la reforma de la administración ambiental a nivel nacional. Esta nueva institución, que nace con el reto de introducir la conciencia ambiental en el modelo alternativo de desarrollo diseñado en el Plan de la Patria 2013-2019, tiene como una de sus tareas principales, el suministro de información ambiental al público en general.
            </p>
            <p>
              Con la promulgación del Decreto Extraordinario N° 6.382 de fecha 15 de junio de 2018, a través del cual se creó el Ministerio del Poder Popular para el Ecosocialismo (MINEC) y el Ministerio de Atención.
            </p>
          </div>
          <div class="col-12 col-md-6">
            <h3 class="text-center">Misión</h3>
            <p>
              Somos el órgano encargado de proteger, conservar y recuperar el ambiente, mediante la construcción del nuevo modelo Ecosocialista, basado en una relación armónica entre el hombre y la naturaleza, que garantice el uso y aprovechamiento racional, óptimo y sostenible de los recursos naturales, respetando los procesos y ciclos de la naturaleza.
            </p>
          </div>
          <div class="col-12 col-md-6">
            <h3 class="text-center">Visión</h3>
            <p>
              Somos el órgano encargado de proteger, conservar y recuperar el ambiente, mediante la construcción del nuevo modelo Ecosocialista, basado en una relación armónica entre el hombre y la naturaleza, que garantice el uso y aprovechamiento racional, óptimo y sostenible de los recursos naturales, respetando los procesos y ciclos de la naturaleza.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-3 px-4">
      <h2 class="text-center">Nuestro Equipo</h2>
      <div class="row">
        <div class="col-12 col-md-4">
          <div>
            <img src="../assets/img/division-gestion-interna.jpeg" class="img-fluid" alt="División Gestión Interna">
          </div>
          <strong class="d-block text-center m-3">DIVISIÓN GESTIÓN INTERNA</strong>
        </div>
        <div class="col-12 col-md-4">
          <div>
            <img src="../assets/img/disivision-de-ambiente.jpeg" class="img-fluid" alt="División de Ambiente">
          </div>
          <strong class="d-block text-center m-3">DIVISIÓN DE AMBIENTE</strong>
        </div>
        <div class="col-12 col-md-4">
          <div>
            <img src="../assets/img/division-de-desechos-solidos.jpeg" class="img-fluid" alt="División Desechos Sólidos">
          </div>
          <strong class="d-block text-center m-3">DIVISIÓN DE DESECHOS SÓLIDOS</strong>
        </div>
      </div>
    </div>
    <div id="contacto" class="mt-2">
      <h2 class="text-center mb-3 text-white">Cotactanos</h2>
      <div class="row">
        <div class="col-12 col-md-8 mx-auto">
          <div class="card p-4">
            <form>
              <div class="form-row">
                <div class="col-12 col-md-6 mb-2">
                  <label class="w-100">
                    Nombre
                    <input type="text" class="form-control" required>
                  </label>
                </div>
                <div class="col-12 col-md-6 mb-2">
                  <label class="w-100">
                    Apellido
                    <input type="text" class="form-control" required>
                  </label>
                </div>
                <div class="col-12 col-md-6 mb-2">
                  <label class="w-100">
                    Correo
                    <input type="email" class="form-control" required>
                  </label>
                </div>
                <div class="col-12 col-md-6 mb-2">
                  <label class="w-100">
                    Teléfono
                    <input type="text" class="form-control" required>
                  </label>
                </div>
                <div class="col-12 mb-2">
                  <label class="w-100">
                    Asunto
                    <input type="text" class="form-control" required>
                  </label>
                </div>
                <div class="col-12 mb-2">
                  <label class="w-100">
                    Mensaje
                    <textarea class="form-control" required></textarea>
                  </label>
                </div>
              </div>
              <button type="submit" class="btn btn-success btn-block">Enviar</button>
            </form>
          </div>
        </div>
      </div>
    </div>
    <div class="bg-light d-flex justify-content-between align-items-center px-3">
      <div class="p-2 logo">
        <img src="../assets/img/logo-minec.png" alt="logo" class="img-fluid">
      </div>
      <div>
        <strong>
          Ulneiver Ramses Mejia Cañizales
        </strong>
      </div>
    </div>

    <!-- Modal Detalles del Servicio-->
    <b-modal id="detallesServicio" hide-footer>
      <h3 class="text-center">{{ detallesServicio.titulo }}</h3>
      <p>{{ detallesServicio.parrafo }}</p>
    </b-modal>

    <!-- Modal Agregar Servicio-->
    <b-modal id="agregarServicio" hide-footer>
      <form>
        <div class="form-group">
          <label>Titulo del Servicio</label>
          <input type="text" class="form-control" v-model="nuevoServicio.titulo">
        </div>
        <div class="form-group">
          <label>Descripción del Servicio</label>
          <textarea class="form-control" v-model="nuevoServicio.parrafo"></textarea>
        </div>
      </form>
      <div class="modal-footer d-flex justify-content-between">
        <button type="button" class="btn btn-secondary" @click="$bvModal.hide('agregarServicio')">Cerrar</button>
        <button type="submit" class="btn btn-success" data-dismiss="modal" @click="agregarServicio">Agregar Servicio</button>
      </div>
    </b-modal>
  </div>
</template>

<script>

export default {
  name: 'Inicio',
  data() {
    return {
      servicios: [
        {
          id: '1',
          titulo: 'AUTORIZACIÓN RACDA',
          parrafo: 'La autorización para el Manejo de Sustancias, Materiales y Desechos Peligrosos y el Registro de Actividades Capaces de Degradar el Ambiente (RACDA), se otorga conforme al Ordenamiento Jurídico Ambiental, a las personas naturales, jurídicas, públicas o privadas que pretendan realizar actividades de manejo o generen materiales y desechos peligrosos, emisiones atmosféricas o efluentes líquidos,  como instrumentos que permiten el establecimiento del control administrativo y técnico, aportando medidas de seguridad, prevención y control de los riesgos en la ejecución de la actividad, en salvaguarda de  la salud y del ambiente.',
        },
        {
          id: '2',
          titulo: 'SISTEMA DE CONSTANCIA DE TRABAJO, RECIBOS DE PAGO Y ARC',
          parrafo: 'Con el objetivo principal de facilitarles a los funcionarios activos y a todos aquellos que hayan prestado servicio en la Institución, el MINEC pone a disposición una aplicación web, en la cual podrán descargar sus respectivos recibos de pago, constancias de trabajo y comprobantes ARC para la declaración de impuesto sobre la renta (ISRL) ante el portal del SENIAT. Link de la aplicación: http://arc.minec.gob.ve',
        },
        {
          id: '3',
          titulo: 'AUTORIZACIÓN PARA IMPORTAR GASES REFRIGERANTES',
          parrafo: 'Solicitud de Autorización por parte de las empresas importadoras de Gases Refrigerantes del tipo Hidrofluorocarbonos (HFC) e Hidroclorofluorocarbonos (HCFC), ante la Dirección General de Gestión de la Calidad Ambiental.',
        },
      ],
      nuevoServicio: {
        titulo: '',
        parrafo: '',
      },
      detallesServicio: {},
      slide: 0,
      sliding: null,
    };
  },
  methods: {
    agregarServicio() {
      if (this.nuevoServicio.id) {
        this.editarServicio();
      } else {
        this.nuevoServicio.id = this.servicios.length + 1;
        this.servicios.push(this.nuevoServicio);
        this.nuevoServicio = {};
        this.$bvModal.hide('agregarServicio');
      }
    },
    editarServicio() {
      this.servicios.forEach((s) => {
        if (s.id == this.nuevoServicio.id) {
          s.titulo = this.nuevoServicio.titulo;
          s.parrafo = this.nuevoServicio.parrafo;
          this.$bvModal.hide('agregarServicio');
        }
      });
    },
    eliminarServicio(i) {
      this.servicios.splice(i, 1)
    },
    onSlideStart() {
      this.sliding = true
    },
    onSlideEnd() {
      this.sliding = false
    }
  },
}
</script>
<style>
  html {
    scroll-behavior: smooth;
  }

  #nosotros {
    background: #283c86;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to left, #45a247, #283c86);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to left, #45a247, #283c86); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    color: white;
    padding: 2rem;
  }

  #contacto {
    background: #283c86;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #45a247, #283c86);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #45a247, #283c86); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    padding: 1rem 2rem;
  }

  .cursor-pointer {
    cursor: pointer;
  }

  .modal-header {
    border: 0 !important;
    padding: 1rem 1.5rem 0 !important;
  }

  .modal-body {
    padding: 0 2rem !important;
  }

  .modal-footer {
    border: 0 !important;
    padding: 1rem 2rem !important;
  }

  .logo {
    width: 120px;
    height: 90px;
  }
</style>