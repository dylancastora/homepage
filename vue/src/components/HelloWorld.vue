<template>
  <div class='hello'>
    <div class='container-fluid section'>

    </div>
    <div class='container-fluid blue section'>
      <div class='container'>
        <div
          v-for='project in projects'
          :key='project.nid[0].value'
          class='row'>
          <div class='col-md-6'>
            <h3 class='white'>{{ project.title[0].value }}</h3>
            <b-badge
              pill 
              v-for='skill in project.field_skills'
              :key='skill.value'
              variant='light'
              class='pill'>{{ skill.value }}</b-badge>
            <br>
            <em class='trans-white'>Published {{ project.field_date[0].value | formatDate }}</em>
            <br>
            <p class='trans-white'>{{ project.field_description[0].value }}</p>
          </div>
          <div class='col-md-6'>
            <b-img fluid
            :src='project.field_image[0].url'
            ></b-img>
            <br>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import moment from 'moment'

const apiURL = 'http://drupal.docker.localhost:8000/api/projects?_format=json'

export default {
  name: 'HelloWorld',
  data () {
    return {
      projects: {}
    }
  },
  filters: {
    formatDate: function (date) {
      return moment(date).format('MMMM, YYYY')
    }
  },
  created () {
    axios
      .get(apiURL)
      .then(response => (this.projects = response.data))
  }
}
</script>
