<template>
  <div id="app" class="professional-app">
    <Header />
    <HeroSection />
    <FeaturesSection />
    <TechSpecs />
    <Roadmap />
    <TeamSection />
    <ContactSection />
    <Footer />
    
    <!-- Enhanced Scroll to Top -->
    <button 
      v-if="showScrollTop" 
      @click="scrollToTop"
      class="scroll-top-btn hover-3d"
    >
      <i class="fas fa-chevron-up"></i>
    </button>
    
    <!-- Background Elements -->
    <div class="bg-gradient"></div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import TechSpecs from './components/TechSpecs.vue'
import Roadmap from './components/Roadmap.vue'
import TeamSection from './components/TeamSection.vue'
import ContactSection from './components/ContactSection.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header, HeroSection, FeaturesSection, TechSpecs, 
    Roadmap, TeamSection, ContactSection, Footer
  },
  data() {
    return {
      showScrollTop: false
    }
  },
  methods: {
    handleScroll() {
      this.showScrollTop = window.scrollY > 300
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped>
.professional-app {
  min-height: 100vh;
  position: relative;
  overflow-x: hidden;
}

.scroll-top-btn {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--neon-blue) 0%, var(--electric-cyan) 100%);
  border: none;
  border-radius: 50%;
  color: var(--pure-white);
  font-size: 1.25rem;
  cursor: pointer;
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
}

.bg-gradient {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: 
    radial-gradient(circle at 20% 80%, rgba(0, 245, 212, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(0, 102, 255, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 40% 40%, rgba(245, 158, 11, 0.05) 0%, transparent 50%);
  z-index: -1;
  pointer-events: none;
}
</style>