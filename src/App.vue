<template>
    <Profile/>
    <Projects/>
</template>

<script>
import Projects from './components/Projects.vue'
import Profile from "@/components/Profile.vue";

export default {
  name: 'App',
  components: {
      Profile,
      Projects
  }
}
</script>

