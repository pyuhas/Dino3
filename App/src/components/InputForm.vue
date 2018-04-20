<template lang="html">
  <div class='InputForm'>
    <form>
      <label>Apply Here: </label>
      <textarea id="application-text" rows="8" cols="100" v-model="applicationText"></textarea>
      <input id="submit" type="submit" value="Submit" @click.prevent.reset="submitApplication" />
    </form>
    <p id="message">{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  props: {
    getText: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      applicationText: '',
      message: ''
    }
  },
  watch: {
    applicationText (newText) {
      this.getText(newText)
    }
  },
  methods: {
    submitApplication(){
      this.message = 'Your application was submitted!',
      this.applicationText = ''
    }
  }
}
</script>

<style scoped>
  form {
    display: block;
    color: #1b997a;
  }
</style>
