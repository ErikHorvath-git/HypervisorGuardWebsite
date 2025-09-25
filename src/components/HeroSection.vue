<template>
  <section class="hero-section section-spacing">
    <div class="container">
      <div class="hero-content">
        <!-- Main Hero Text -->
        <div class="hero-text">
          <div class="badge">LOCAL AI SECURITY SOLUTION</div>
          <h1 class="hero-title gradient-text-cyan">
            AI RAM Analyzer
          </h1>
          <h2 class="hero-subtitle">
            Real-time <span class="gradient-text-amber">Threat Detection</span> & Response
          </h2>
          <p class="hero-description body-large">
            Hypervisor-powered memory analysis for critical infrastructure protection. 
            Detect and block advanced APT threats in real-time with complete data sovereignty 
            and no cloud dependency.
          </p>
          
          <!-- CTA Buttons -->
          <div class="hero-actions">
            <button class="btn-primary">
              <i class="fas fa-play mr-3"></i>
              View Demo
            </button>
            <button class="btn-secondary">
              <i class="fas fa-shield-alt mr-3"></i>
              Technical Specs
            </button>
          </div>
        </div>
        
        <!-- Stats Grid -->
        <div class="hero-stats">
          <div class="stats-disclaimer">
            <i class="fas fa-bullseye mr-2"></i>
            Targeted Performance Benchmarks
          </div>
          <div v-for="stat in stats" :key="stat.id" class="stat-card glass-morphism hover-3d">
            <div class="stat-icon icon-container icon-lg" :class="stat.iconColor">
              <i :class="stat.icon"></i>
            </div>
            <div class="stat-content">
              <div class="stat-number">{{ stat.value }}</div>
              <div class="stat-label">{{ stat.label }}</div>
              <div class="stat-target">Project Target</div>
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
          value: '99%',
          label: 'Detection Rate',
          trend: 'APT threats',
          trendIcon: 'fas fa-bullseye',
          trendClass: 'trend-target'
        },
        {
          id: 2,
          icon: 'fas fa-chart-line',
          iconColor: 'icon-emerald',
          value: '<1%',
          label: 'False Positives',
          trend: 'Target benchmark',
          trendIcon: 'fas fa-bullseye',
          trendClass: 'trend-target'
        },
        {
          id: 3,
          icon: 'fas fa-shield-alt',
          iconColor: 'icon-cyan',
          value: '<500ms',
          label: 'Response Time',
          trend: 'Project goal',
          trendIcon: 'fas fa-bullseye',
          trendClass: 'trend-target'
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
  position: relative;
}

.stats-disclaimer {
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(245, 158, 11, 0.1);
  color: var(--amber-glow);
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-size: 0.875rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.stat-card {
  padding: 2rem;
  display: flex;
  align-items: center;
  gap: 1.5rem;
  transition: all 0.4s ease;
  position: relative;
}

.stat-content {
  flex: 1;
}

.stat-number {
  position: relative;
}

.stat-label {
  color: var(--steel-gray);
  font-weight: 500;
  margin-bottom: 0.25rem;
}

.stat-target {
  font-size: 0.75rem;
  color: var(--amber-glow);
  font-weight: 600;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.stat-trend {
  font-size: 0.875rem;
  font-weight: 600;
}

.trend-target {
  color: var(--amber-glow);
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
  
  .stats-disclaimer {
    text-align: center;
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
  
  .stats-disclaimer {
    font-size: 0.8rem;
    padding: 0.5rem 1rem;
  }
}
</style>