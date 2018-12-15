<template>
  <div class='hello'>
    <div class='container-fluid'>
      <div class='container'>
        <div
        v-for='project in projects'
        :key='project.nid[0].value'>
          <h2>{{project.title[0].value}}</h2>
          <p>Published {{project.field_date[0].value}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

const apiURL = 'http://drupal.docker.localhost:8000/api/projects?_format=json'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      projects: []
    }
  },
  mounted () {
    axios
      .get(apiURL)
      .then(response => (this.projects = response.data))
  }
}
</script>
