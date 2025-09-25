<template>
  <section id="features" class="features-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">ADVANCED SECURITY CAPABILITIES</div>
        <h2 class="section-title gradient-text-cyan">
          Core Features
        </h2>
        <p class="section-description body-large text-overflow-fix">
          Hypervisor-powered RAM analysis for real-time APT threat detection and response.
        </p>
      </div>

      <!-- Features Grid -->
      <div class="features-grid">
        <div v-for="feature in features" :key="feature.id" class="feature-card glass-morphism hover-3d">
          <div class="feature-icon-container">
            <div class="icon-container icon-xl" :class="feature.iconColor">
              <i :class="feature.icon"></i>
            </div>
            <div class="feature-badge">{{ feature.badge }}</div>
          </div>
          
          <div class="feature-content">
            <h3 class="feature-title text-overflow-fix">{{ feature.title }}</h3>
            <p class="feature-description text-overflow-fix">{{ feature.description }}</p>
            
            <ul class="feature-benefits">
              <li v-for="benefit in feature.benefits" :key="benefit" class="text-overflow-fix">
                <i class="fas fa-check"></i>
                <span>{{ benefit }}</span>
              </li>
            </ul>
            
            <div class="feature-cta">
              <button class="feature-link">
                Learn More <i class="fas fa-arrow-right"></i>
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Stats Bar -->
      <div class="features-stats glass-morphism">
        <div v-for="stat in stats" :key="stat.id" class="stat-item">
          <div class="stat-value gradient-text-cyan">{{ stat.value }}</div>
          <div class="stat-label">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturesSection',
  data() {
    return {
      features: [
        {
          id: 1,
          icon: 'fas fa-brain',
          iconColor: 'icon-cyan',
          badge: 'AI-Powered',
          title: 'APT Threat Detection',
          description: 'Advanced AI algorithms detect sophisticated APT techniques in real-time memory analysis.',
          benefits: [
            'Behavioral anomaly detection',
            'Zero-day threat identification',
            'Advanced pattern recognition'
          ]
        },
        {
          id: 2,
          icon: 'fas fa-bolt',
          iconColor: 'icon-amber',
          badge: 'Real-Time',
          title: 'Hypervisor Monitoring',
          description: 'Continuous ring-0 level RAM monitoring with immediate threat response capabilities.',
          benefits: [
            'VMX/VMCS management',
            'EPT-based memory access',
            'Instant containment actions'
          ]
        },
        {
          id: 3,
          icon: 'fas fa-shield-alt',
          iconColor: 'icon-emerald',
          badge: 'Local Security',
          title: 'Data Sovereignty',
          description: 'Complete local deployment ensuring no cloud dependency or data sharing risks.',
          benefits: [
            'GDPR/NIS2 compliance',
            'No external data transfer',
            'Full control over sensitive data'
          ]
        },
        {
          id: 4,
          icon: 'fas fa-chart-pie',
          iconColor: 'icon-cyan',
          badge: 'Forensic',
          title: 'RAM Forensics',
          description: 'Deep memory analysis for uncovering hidden processes and sophisticated attacks.',
          benefits: [
            'Process hollowing detection',
            'Unlinked DLL identification',
            'RWX page monitoring'
          ]
        },
        {
          id: 5,
          icon: 'fas fa-robot',
          iconColor: 'icon-amber',
          badge: 'Automation',
          title: 'Auto-Containment',
          description: 'Automated response actions to isolate threats without service interruption.',
          benefits: [
            'Thread suspension',
            'EPT access revocation',
            'System call blocking'
          ]
        },
        {
          id: 6,
          icon: 'fas fa-server',
          iconColor: 'icon-emerald',
          badge: 'Critical Infrastructure',
          title: 'Enterprise Protection',
          description: 'Designed specifically for critical infrastructure with high availability requirements.',
          benefits: [
            '99.5% uptime guarantee',
            'Critical infrastructure focus',
            'EU regulatory alignment'
          ]
        }
      ],
      stats: [
        { id: 1, value: '99%', label: 'Detection Rate' },
        { id: 2, value: '<1%', label: 'False Positives' },
        { id: 3, value: '<500ms', label: 'Response Time' },
        { id: 4, value: '0%', label: 'Cloud Risk' }
      ]
    }
  }
}
</script>

<style scoped>
.features-section {
  background: linear-gradient(180deg, var(--deep-space) 0%, rgba(15, 23, 42, 0.8) 100%);
}

.section-header {
  text-align: center;
  max-width: 100%;
  margin: 0 auto 3rem;
  padding: 0 1rem;
}

.section-badge {
  display: inline-block;
  background: rgba(0, 245, 212, 0.1);
  color: var(--electric-cyan);
  padding: 0.5rem 1.25rem;
  border-radius: 50px;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  margin-bottom: 1rem;
}

.section-description {
  color: var(--steel-gray);
  font-size: 1.1rem;
  line-height: 1.5;
}

.features-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.feature-card {
  padding: 1.5rem;
  margin: 0 0.5rem;
}

.feature-icon-container {
  position: relative;
  margin-bottom: 1rem;
  text-align: center;
}

.feature-badge {
  position: absolute;
  top: -8px;
  right: -8px;
  background: var(--amber-glow);
  color: var(--deep-space);
  padding: 0.25rem 0.5rem;
  border-radius: 15px;
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
}

.feature-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
  color: var(--pure-white);
  text-align: center;
}

.feature-description {
  color: var(--steel-gray);
  margin-bottom: 1rem;
  line-height: 1.5;
  text-align: center;
}

.feature-benefits {
  list-style: none;
  margin-bottom: 1.5rem;
}

.feature-benefits li {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
  color: var(--steel-gray);
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
  line-height: 1.4;
}

.feature-benefits i {
  color: var(--emerald-pulse);
  font-size: 0.8rem;
  min-width: 16px;
  margin-top: 0.2rem;
}

.feature-benefits span {
  flex: 1;
}

.feature-link {
  background: none;
  border: none;
  color: var(--electric-cyan);
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  width: 100%;
  padding: 0.75rem;
  font-size: 0.9rem;
}

.feature-link i {
  transition: transform 0.3s ease;
}

.feature-link:hover i {
  transform: translateX(3px);
}

.features-stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
  padding: 2rem 1rem;
  margin: 0 0.5rem;
}

.stat-item {
  padding: 0.5rem;
  text-align: center;
}

.stat-value {
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 0.25rem;
}

.stat-label {
  color: var(--steel-gray);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 0.75rem;
}

/* Desktop styles */
@media (min-width: 768px) {
  .section-header {
    max-width: 800px;
    margin: 0 auto 6rem;
    padding: 0;
  }
  
  .features-grid {
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
    margin-bottom: 6rem;
  }
  
  .feature-card {
    padding: 2.5rem;
    margin: 0;
  }
  
  .feature-icon-container {
    text-align: left;
    margin-bottom: 1.5rem;
  }
  
  .feature-title {
    text-align: left;
    font-size: 1.5rem;
  }
  
  .feature-description {
    text-align: left;
  }
  
  .features-stats {
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    padding: 3rem 2rem;
    margin: 0;
  }
  
  .stat-value {
    font-size: 3rem;
  }
}

@media (min-width: 1024px) {
  .features-grid {
    gap: 3rem;
  }
}
</style>