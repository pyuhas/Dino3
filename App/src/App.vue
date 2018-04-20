<template>
  <div id='app'>
    <Header></Header>
    <main>
      <JobDetails :jobData="jobDetails"></JobDetails>
      <InputForm :getText="getText"></InputForm>
      <button id="preview-toggle" @click='togglePreview = !togglePreview'>Show Preview</button>
      <Preview :text="applicationText" :class='{hidden : togglePreview}'></Preview>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import InputForm from './components/InputForm.vue'
import JobDetails from './components/JobDetails.vue'
import Preview from './components/Preview.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Header,
    InputForm,
    JobDetails,
    Preview,
    Footer
  },
  data () {
    return {
      togglePreview: true,
      applicationText: '',
      jobDetails: {}
    }
  },
  created() {
    fetch('../../static/listing.json')
    .then(response => response.json())
    .then(response => {
      this.jobDetails = response
    })
  },
  methods: {
    getText(text) {
      this.applicationText = text;
    }
  }
}
</script>

<style>
* {
  margin: 10;
  padding: 10;
}
#app {
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
main {
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}
.hidden {
  display: none;
}
</style>
