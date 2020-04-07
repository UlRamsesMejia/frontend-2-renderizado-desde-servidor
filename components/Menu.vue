<template>
  <div>
    <b-navbar toggleable="md" type="dark" variant="success">
      <nuxt-link class="navbar-brand text-center" to="/">
        Ministerio del Poder <br class="d-lg-none" />Popular para el Ecosocialismo
      </nuxt-link>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="/#servicios">SERVICIOS</b-nav-item>
          <b-nav-item href="/#nosotros">NOSOTROS</b-nav-item>
          <b-nav-item href="/#contacto">CONTACTO</b-nav-item>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/noticias">NOTICIAS</nuxt-link>
          </li>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<style>
  .nav-link {
    color: white !important;
  }
  .nav-link:hover {
    color: #6c757d !important;
  }
</style>