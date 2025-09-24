<template>
  <section class="hero-section section-spacing">
    <div class="container">
      <div class="hero-content">
        <!-- Main Hero Text -->
        <div class="hero-text">
          <div class="badge">ENTERPRISE AI PLATFORM</div>
          <h1 class="hero-title gradient-text-cyan">
            Hypervisor AI
          </h1>
          <h2 class="hero-subtitle">
            Revolutionary <span class="gradient-text-amber">RAM Analysis</span> Platform
          </h2>
          <p class="hero-description body-large">
            AI-powered memory analysis for enterprise virtualization. 
            Detect, predict, and optimize RAM usage across your entire 
            hypervisor infrastructure with unprecedented accuracy.
          </p>
          
          <!-- CTA Buttons -->
          <div class="hero-actions">
            <button class="btn-primary">
              <i class="fas fa-play mr-3"></i>
              Live Demo
            </button>
            <button class="btn-secondary">
              <i class="fas fa-chart-bar mr-3"></i>
              View Analytics
            </button>
          </div>
        </div>
        
        <!-- Stats Grid -->
        <div class="hero-stats">
          <div v-for="stat in stats" :key="stat.id" class="stat-card glass-morphism hover-3d">
            <div class="stat-icon icon-container icon-lg" :class="stat.iconColor">
              <i :class="stat.icon"></i>
            </div>
            <div class="stat-content">
              <div class="stat-number">{{ stat.value }}</div>
              <div class="stat-label">{{ stat.label }}</div>
              <div class="stat-trend" :class="stat.trendClass">
                <i :class="stat.trendIcon"></i>
                {{ stat.trend }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
  data() {
    return {
      stats: [
        {
          id: 1,
          icon: 'fas fa-bolt',
          iconColor: 'icon-amber',
          value: '90%',
          label: 'Faster Analysis',
          trend: '+15% efficiency',
          trendIcon: 'fas fa-arrow-up',
          trendClass: 'trend-positive'
        },
        {
          id: 2,
          icon: 'fas fa-chart-line',
          iconColor: 'icon-emerald',
          value: '60%',
          label: 'Cost Reduction',
          trend: '$2.3M saved',
          trendIcon: 'fas fa-dollar-sign',
          trendClass: 'trend-positive'
        },
        {
          id: 3,
          icon: 'fas fa-shield-alt',
          iconColor: 'icon-cyan',
          value: '99.9%',
          label: 'Prediction Accuracy',
          trend: 'Industry leading',
          trendIcon: 'fas fa-trophy',
          trendClass: 'trend-premium'
        }
      ]
    }
  }
}
</script>

<style scoped>
.hero-section {
  padding-top: 12rem;
  position: relative;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-text {
  max-width: 600px;
}

.badge {
  display: inline-block;
  background: rgba(0, 245, 212, 0.1);
  color: var(--electric-cyan);
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  font-size: 0.875rem;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  margin-bottom: 2rem;
}

.hero-subtitle {
  font-size: clamp(1.5rem, 4vw, 2.5rem);
  font-weight: 600;
  margin: 1rem 0 2rem;
  color: var(--cloud-gray);
}

.hero-description {
  color: var(--steel-gray);
  margin-bottom: 3rem;
  font-size: 1.25rem;
}

.hero-actions {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.hero-stats {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.stat-card {
  padding: 2rem;
  display: flex;
  align-items: center;
  gap: 1.5rem;
  transition: all 0.4s ease;
}

.stat-content {
  flex: 1;
}

.stat-label {
  color: var(--steel-gray);
  font-weight: 500;
  margin-bottom: 0.5rem;
}

.stat-trend {
  font-size: 0.875rem;
  font-weight: 600;
}

.trend-positive {
  color: var(--emerald-pulse);
}

.trend-premium {
  color: var(--amber-glow);
}

/* Responsive Design */
@media (max-width: 968px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }
  
  .hero-actions {
    justify-content: center;
  }
  
  .stat-card {
    text-align: left;
  }
}

@media (max-width: 480px) {
  .hero-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .hero-actions button {
    width: 100%;
    max-width: 300px;
  }
}
</style>