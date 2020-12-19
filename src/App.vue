<template>
  <Navbar />
  <Main />
</template>

<script>
import Main from './components/Main.vue'
import Navbar from './components/Navbar.vue'


export default {
  name: 'App',
  components: {
    Navbar,
    Main,
  }
}
</script>
