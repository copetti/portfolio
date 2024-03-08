<template>
    <Profile/>
    <Projects/>
    <Footer></Footer>
</template>

<script>
import Projects from '@/components/Projects.vue'
import Profile from "@/components/Profile.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: 'App',
  components: {
      Footer,
      Profile,
      Projects
  }
}
</script>

