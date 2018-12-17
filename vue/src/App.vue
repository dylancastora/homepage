<template>
  <div>
    <b-navbar toggleable='md' v-bind:class='{red:red, blue:blue, brown:brown, olive:olive}' type='dark'>
      <div class='container'>
        <b-navbar-brand href='#' class='name' @mouseover='mouseOverDylan'>Dylan Castora</b-navbar-brand>
        <b-navbar-toggle target='nav_collapse'></b-navbar-toggle>
        <b-collapse is-nav id='nav_collapse'>
          <b-navbar-nav class='ml-auto'>
            <b-nav-item href='#' @mouseover='mouseOverTech'>Tech</b-nav-item>
            <b-nav-item href='#' @mouseover='mouseOverMusic'>Music</b-nav-item>
            <b-nav-item href='#' @mouseover='mouseOverContact'>Contact</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </b-navbar>
    <div id='app'>
      <router-view/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      red: true,
      blue: false,
      brown: false

    }
  },
  methods: {
    mouseOverDylan: function () {
      this.red = true
      this.blue = false
      this.brown = false
      this.olive = false
    },
    mouseOverTech: function () {
      this.red = false
      this.blue = true
      this.brown = false
      this.olive = false
    },
    mouseOverMusic: function () {
      this.red = false
      this.blue = false
      this.brown = true
      this.olive = false
    },
    mouseOverContact: function () {
      this.red = false
      this.blue = false
      this.brown = false
      this.olive = true
    }
  }
}
</script>

<style>
h3 {
  font-family: 'Rubik', sans-serif;
}
.trans-white {
  color: rgba(255, 255, 255, 0.5);
}
.white {
  color: #ffffff;
}
.pill {
  margin: 0 2px 0 2px;
}
.name {
  font-family: 'Rubik', sans-serif;
}
.section {
  padding-top: 20px;
  padding-bottom: 20px;
}
.red {
  background-color: #b86565;
}
.blue {
  background-color: #485b7a;
}
.brown {
  background-color: #a79a8f;
}
.beige {
  background-color: #dfd8d1;
}
.olive {
  background-color: #6b8e23;
}
</style>
