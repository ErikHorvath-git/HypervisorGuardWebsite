<template>
  <section id="features" class="features-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">POWERFUL CAPABILITIES</div>
        <h2 class="section-title gradient-text-cyan">
          Enterprise-Grade Features
        </h2>
        <p class="section-description body-large">
          Advanced AI capabilities designed specifically for hypervisor memory management 
          and optimization at scale.
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
            <h3 class="feature-title">{{ feature.title }}</h3>
            <p class="feature-description">{{ feature.description }}</p>
            
            <ul class="feature-benefits">
              <li v-for="benefit in feature.benefits" :key="benefit">
                <i class="fas fa-check-circle"></i>
                {{ benefit }}
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
          title: 'Predictive Memory Analysis',
          description: 'Machine learning algorithms that anticipate memory usage patterns and prevent bottlenecks before they impact performance.',
          benefits: [
            'Real-time anomaly detection',
            'Predictive capacity planning',
            'Automated optimization suggestions'
          ]
        },
        {
          id: 2,
          icon: 'fas fa-bolt',
          iconColor: 'icon-amber',
          badge: 'Real-Time',
          title: 'Live Performance Monitoring',
          description: 'Continuous monitoring of RAM usage across all virtual machines with instant alerts and actionable insights.',
          benefits: [
            'Sub-second latency monitoring',
            'Smart alert system',
            'Historical performance tracking'
          ]
        },
        {
          id: 3,
          icon: 'fas fa-shield-alt',
          iconColor: 'icon-emerald',
          badge: 'Security',
          title: 'Advanced Threat Detection',
          description: 'Identify memory-based security threats and vulnerabilities with behavioral analysis and threat intelligence.',
          benefits: [
            'Memory intrusion detection',
            'Behavioral anomaly analysis',
            'Compliance reporting'
          ]
        },
        {
          id: 4,
          icon: 'fas fa-chart-network',
          iconColor: 'icon-cyan',
          badge: 'Analytics',
          title: 'Intelligent Reporting',
          description: 'Comprehensive dashboards and customizable reports for deep insights into memory utilization patterns.',
          benefits: [
            'Custom report builder',
            'Export to multiple formats',
            'Scheduled reporting'
          ]
        },
        {
          id: 5,
          icon: 'fas fa-robot',
          iconColor: 'icon-amber',
          badge: 'Automation',
          title: 'Smart Optimization',
          description: 'Automated memory balancing and resource allocation based on AI-driven recommendations.',
          benefits: [
            'One-click optimization',
            'Custom automation rules',
            'Performance forecasting'
          ]
        },
        {
          id: 6,
          icon: 'fas fa-infinity',
          iconColor: 'icon-emerald',
          badge: 'Scalability',
          title: 'Enterprise Scaling',
          description: 'Designed to scale from single servers to global data center deployments without performance loss.',
          benefits: [
            'Multi-tenant architecture',
            'Global deployment ready',
            'Unlimited scaling capacity'
          ]
        }
      ],
      stats: [
        { id: 1, value: '10x', label: 'Faster Analysis' },
        { id: 2, value: '99.9%', label: 'Uptime SLA' },
        { id: 3, value: '60%', label: 'Cost Reduction' },
        { id: 4, value: '24/7', label: 'Support' }
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
  max-width: 800px;
  margin: 0 auto 6rem;
}

.section-badge {
  display: inline-block;
  background: rgba(0, 245, 212, 0.1);
  color: var(--electric-cyan);
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  font-size: 0.875rem;
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  margin-bottom: 1.5rem;
}

.section-description {
  color: var(--steel-gray);
  font-size: 1.25rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 2rem;
  margin-bottom: 6rem;
}

.feature-card {
  padding: 2.5rem;
  transition: all 0.4s ease;
}

.feature-icon-container {
  position: relative;
  margin-bottom: 1.5rem;
}

.feature-badge {
  position: absolute;
  top: -10px;
  right: -10px;
  background: var(--amber-glow);
  color: var(--deep-space);
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
}

.feature-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--pure-white);
}

.feature-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.feature-benefits {
  list-style: none;
  margin-bottom: 2rem;
}

.feature-benefits li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--steel-gray);
  margin-bottom: 0.5rem;
}

.feature-benefits i {
  color: var(--emerald-pulse);
}

.feature-link {
  background: none;
  border: none;
  color: var(--electric-cyan);
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.feature-link:hover {
  gap: 0.5rem;
}

.feature-link i {
  transition: transform 0.3s ease;
}

.feature-link:hover i {
  transform: translateX(5px);
}

.features-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  padding: 3rem 2rem;
  text-align: center;
}

.stat-item {
  padding: 1rem;
}

.stat-value {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
}

.stat-label {
  color: var(--steel-gray);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 0.875rem;
}

@media (max-width: 768px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
  
  .feature-card {
    padding: 2rem;
  }
  
  .features-stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
}
</style>