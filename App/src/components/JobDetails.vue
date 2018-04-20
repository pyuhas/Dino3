<template lang="html">
  <div class='JobDetails'>
    <section id='job-details'>
      <h2>Job Details</h2>
      <h4>Demolitions Manager</h4>
      <p>Please destroy things for us.</p>
      <h4>{{jobData.title}}</h4>
      <p>
        {{jobData.description}}
      </p>
    </section>
  </div>
</template>
<script>
export default {
  name: 'JobDetails',
  props: ['jobData']
}
</script>
<style scoped>
#job-details {
  margin: 0 30px 0 30px;
  font-family: sans-serif;
  color: #1b997a;
}
</style>
