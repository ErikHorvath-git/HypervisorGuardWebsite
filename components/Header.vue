<template>
  <header class="professional-header" :class="{ 'scrolled': isScrolled }">
    <nav class="nav-container">
      <div class="nav-content">
        <!-- Logo -->
        <div class="logo-group">
          <div class="logo-icon icon-container icon-md icon-cyan hover-glow">
            <i class="fas fa-server"></i>
          </div>
          <span class="logo-text gradient-text-cyan">Hypervisor AI</span>
        </div>

        <!-- Navigation -->
        <div class="nav-links">
          <a v-for="item in navItems" :key="item.id" :href="item.href" class="nav-link">
            <span class="link-text">{{ item.text }}</span>
            <div class="link-underline"></div>
          </a>
        </div>

        <!-- CTA -->
        <div class="nav-actions">
          <button class="btn-secondary btn-sm">
            <i class="fas fa-eye mr-2"></i>
            View Demo
          </button>
          <button class="btn-primary btn-sm">
            <i class="fas fa-rocket mr-2"></i>
            Get Started
          </button>
        </div>

        <!-- Mobile Menu -->
        <button class="mobile-menu-btn" @click="toggleMobileMenu">
          <i class="fas fa-bars"></i>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div class="mobile-menu" :class="{ 'active': mobileMenuOpen }">
        <a v-for="item in navItems" :key="item.id" :href="item.href" class="mobile-nav-link">
          {{ item.text }}
        </a>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isScrolled: false,
      mobileMenuOpen: false,
      navItems: [
        { id: 1, text: 'Features', href: '#features' },
        { id: 2, text: 'Technology', href: '#tech' },
        { id: 3, text: 'Roadmap', href: '#roadmap' },
        { id: 4, text: 'Team', href: '#team' },
        { id: 5, text: 'Contact', href: '#contact' }
      ]
    }
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    },
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen
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
.professional-header {
  position: fixed;
  top: 0;
  width: 100%;
  background: rgba(15, 23, 42, 0.8);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  z-index: 1000;
  transition: all 0.4s ease;
}

.professional-header.scrolled {
  background: rgba(15, 23, 42, 0.95);
  border-bottom-color: rgba(0, 245, 212, 0.2);
}

.nav-container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

.nav-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 0;
}

.logo-group {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
}

.nav-links {
  display: flex;
  gap: 2.5rem;
}

.nav-link {
  position: relative;
  color: var(--steel-gray);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  padding: 0.5rem 0;
}

.nav-link:hover {
  color: var(--pure-white);
}

.link-underline {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--electric-cyan);
  transition: width 0.3s ease;
}

.nav-link:hover .link-underline {
  width: 100%;
}

.nav-actions {
  display: flex;
  gap: 1rem;
}

.btn-sm {
  padding: 0.75rem 1.5rem;
  font-size: 0.875rem;
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  color: var(--steel-gray);
  font-size: 1.25rem;
  cursor: pointer;
}

.mobile-menu {
  display: none;
  flex-direction: column;
  background: var(--deep-space);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.mobile-menu.active {
  display: flex;
}

.mobile-nav-link {
  padding: 1rem 2rem;
  color: var(--steel-gray);
  text-decoration: none;
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  transition: all 0.3s ease;
}

.mobile-nav-link:hover {
  color: var(--electric-cyan);
  background: rgba(0, 245, 212, 0.05);
}

@media (max-width: 968px) {
  .nav-links, .nav-actions {
    display: none;
  }
  
  .mobile-menu-btn {
    display: block;
  }
  
  .nav-container {
    padding: 0 1.5rem;
  }
}
</style>