<script>
import AppMain from './components/AppMain.vue'
import ContactForm from './components/ContactForm.vue'

export default {
  components: {
    AppMain,
    ContactForm
  }
}
</script>

<template>
  <div>
    <ContactForm />
  </div>
</template>

<style lang="scss">
@use './styles/generals.scss' as *;
</style>
