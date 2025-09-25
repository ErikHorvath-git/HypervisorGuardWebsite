<template>
  <section id="tech" class="tech-specs-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">HYPERVISOR TECHNOLOGY</div>
        <h2 class="section-title gradient-text-cyan">
          Security Architecture
        </h2>
        <p class="section-description body-large">
          Low-level hypervisor-based RAM analysis for real-time APT threat detection 
          and response with complete data sovereignty.
        </p>
      </div>

      <!-- Architecture Overview -->
      <div class="architecture-overview glass-morphism">
        <div class="architecture-header">
          <h3 class="architecture-title">Hypervisor Security Layers</h3>
          <p class="architecture-subtitle">Ring-0 level protection designed for critical infrastructure</p>
        </div>
        
        <div class="architecture-layers">
          <div v-for="layer in architecture" :key="layer.id" class="architecture-layer" :class="layer.status">
            <div class="layer-header">
              <div class="layer-icon">
                <i :class="layer.icon"></i>
              </div>
              <div class="layer-info">
                <h4 class="layer-name">{{ layer.name }}</h4>
                <div class="layer-tech">{{ layer.technology }}</div>
              </div>
              <div class="layer-badge" :class="layer.status">{{ layer.status }}</div>
            </div>
            
            <p class="layer-description">{{ layer.description }}</p>
            
            <div class="layer-features">
              <div v-for="feature in layer.features" :key="feature" class="feature-item">
                <i class="fas fa-check"></i>
                <span>{{ feature }}</span>
              </div>
            </div>
            
            <div class="layer-performance">
              <div class="performance-metric">
                <div class="metric-value">{{ layer.performance.value }}</div>
                <div class="metric-label">{{ layer.performance.label }}</div>
              </div>
              <div class="performance-bar">
                <div class="performance-fill" :style="{ width: layer.performance.percentage + '%' }"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Technology Stack -->
      <div class="tech-stack-grid">
  <div v-for="category in techStack" :key="category.id" class="tech-category">
    <div class="category-header">
      <div class="category-icon icon-container icon-lg" :class="category.iconColor">
        <i :class="category.icon"></i>
      </div>
      <h3 class="category-title">{{ category.name }}</h3>
    </div>
    
    <div class="technologies-list">
      <div v-for="tech in category.technologies" :key="tech.name" class="tech-item">
        <div class="tech-logo">
          <i :class="tech.icon"></i>
        </div>
        <div class="tech-info">
          <div class="tech-name">{{ tech.name }}</div>
          <div class="tech-purpose">{{ tech.purpose }}</div>
        </div>
        <div class="tech-rating">
          <div class="rating-stars">
            <i v-for="star in 5" :key="star" 
               :class="star <= tech.rating ? 'fas fa-star' : 'far fa-star'"></i>
          </div>
          <div class="rating-text">{{ tech.rating }}/5</div>
        </div>
      </div>
    </div>
  </div>
</div>

      <!-- Performance Metrics -->
      <div class="performance-section">
        <h3 class="performance-title">Security Performance Metrics</h3>
        <div class="metrics-grid">
          <div v-for="metric in performanceMetrics" :key="metric.id" class="metric-card glass-morphism hover-3d">
            <div class="metric-icon" :style="{ background: metric.color }">
              <i :class="metric.icon"></i>
            </div>
            <div class="metric-content">
              <div class="metric-value">{{ metric.value }}</div>
              <div class="metric-label">{{ metric.label }}</div>
              <div class="metric-trend" :class="metric.trend">
                <i :class="metric.trendIcon"></i>
                {{ metric.trendText }}
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
  name: 'TechSpecs',
  data() {
    return {
      architecture: [
        {
          id: 1,
          name: 'Hypervisor Core',
          technology: 'VMX/VMCS + EPT Management',
          icon: 'fas fa-shield-alt',
          status: 'development',
          description: 'Ring-0 hypervisor with VMX initialization, VMCS management and EPT mapping for secure memory access.',
          features: [
            'VMX root/non-root operation',
            'EPT identity mapping',
            'MSR/CR register trapping',
            'System call monitoring'
          ],
          performance: { value: '<3%', label: 'CPU Overhead', percentage: 97 }
        },
        {
          id: 2,
          name: 'RAM Acquisition',
          technology: 'DMA-safe Memory Dumping',
          icon: 'fas fa-memory',
          status: 'development',
          description: 'Secure memory snapshot collection outside user space with process mapping and hidden module detection.',
          features: [
            'CR3 monitoring',
            'Process mapping',
            'Hidden module detection',
            '<5s snapshot time'
          ],
          performance: { value: '99%', label: 'Memory Coverage', percentage: 99 }
        },
        {
          id: 3,
          name: 'AI Detection Engine',
          technology: 'Machine Learning + YARA',
          icon: 'fas fa-brain',
          status: 'prototype',
          description: 'AI-powered threat detection combining behavioral analysis with signature-based YARA rules.',
          features: [
            'EPT anomaly detection',
            'Process hollowing identification',
            'Unlinked DLL detection',
            'RWX page monitoring'
          ],
          performance: { value: '95%', label: 'Detection Rate', percentage: 95 }
        },
        {
          id: 4,
          name: 'Response Handler',
          technology: 'Auto-Containment System',
          icon: 'fas fa-bolt',
          status: 'planned',
          description: 'Real-time threat response with thread suspension, EPT revocation and system call blocking.',
          features: [
            'Thread suspension',
            'EPT access revocation',
            'Syscall blocking',
            'Snapshot rollback'
          ],
          performance: { value: '<500ms', label: 'Response Time', percentage: 100 }
        }
      ],
      techStack: [
  {
    id: 1,
    name: 'Low-Level Programming',
    icon: 'fas fa-microchip',
    iconColor: 'icon-cyan',
    technologies: [
      { name: 'C/C++', icon: 'fas fa-cogs', purpose: 'Kernel Development', rating: 5 },
      { name: 'Assembly', icon: 'fas fa-code', purpose: 'Hardware Interaction', rating: 4 },
      { name: 'Windows Driver Kit', icon: 'fab fa-windows', purpose: 'Driver Development', rating: 4 },
      { name: 'Linux Kernel API', icon: 'fab fa-linux', purpose: 'Kernel Modules', rating: 5 }
    ]
  },
  {
    id: 2,
    name: 'Security & Forensics',
    icon: 'fas fa-user-secret',
    iconColor: 'icon-amber',
    technologies: [
      { name: 'YARA', icon: 'fas fa-search', purpose: 'Pattern Matching', rating: 5 },
      { name: 'Volatility', icon: 'fas fa-search-plus', purpose: 'Memory Analysis', rating: 5 },
      { name: 'Python', icon: 'fab fa-python', purpose: 'Analysis Scripts', rating: 4 },
      { name: 'Custom ML Models', icon: 'fas fa-robot', purpose: 'Anomaly Detection', rating: 4 }
    ]
  },
  {
    id: 3,
    name: 'Virtualization',
    icon: 'fas fa-server',
    iconColor: 'icon-emerald',
    technologies: [
      { name: 'Intel VMX', icon: 'fas fa-cube', purpose: 'Hardware Virtualization', rating: 5 },
      { name: 'AMD-V', icon: 'fas fa-cube', purpose: 'AMD Virtualization', rating: 5 },
      { name: 'Extended Page Tables', icon: 'fas fa-table', purpose: 'Memory Management', rating: 4 },
      { name: 'VMCS', icon: 'fas fa-database', purpose: 'VM Control Structure', rating: 5 }
    ]
  }
],
      performanceMetrics: [
        {
          id: 1,
          value: '99%',
          label: 'APT Detection Rate',
          icon: 'fas fa-bullseye',
          color: 'linear-gradient(135deg, #00f5d4, #0066ff)',
          trend: 'positive',
          trendIcon: 'fas fa-arrow-up',
          trendText: 'Industry leading'
        },
        {
          id: 2,
          value: '<1%',
          label: 'False Positive Rate',
          icon: 'fas fa-times-circle',
          color: 'linear-gradient(135deg, #f59e0b, #f43f5e)',
          trend: 'positive',
          trendIcon: 'fas fa-arrow-down',
          trendText: 'Minimal false alerts'
        },
        {
          id: 3,
          value: '<500ms',
          label: 'Threat Response Time',
          icon: 'fas fa-tachometer-alt',
          color: 'linear-gradient(135deg, #10b981, #00f5d4)',
          trend: 'stable',
          trendIcon: 'fas fa-bolt',
          trendText: 'Real-time blocking'
        },
        {
          id: 4,
          value: '0%',
          label: 'Cloud Dependency',
          icon: 'fas fa-cloud-slash',
          color: 'linear-gradient(135deg, #8b5cf6, #0066ff)',
          trend: 'positive',
          trendIcon: 'fas fa-check',
          trendText: 'Complete sovereignty'
        }
      ]
    }
  }
}
</script>

<style scoped>
.tech-specs-section {
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.9) 0%, var(--deep-space) 100%);
}

.architecture-overview {
  padding: 3rem;
  margin-bottom: 4rem;
}

.architecture-header {
  text-align: center;
  margin-bottom: 3rem;
}

.architecture-title {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--pure-white);
}

.architecture-subtitle {
  color: var(--steel-gray);
  font-size: 1.125rem;
}

.architecture-layers {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.architecture-layer {
  padding: 2rem;
  background: rgba(255, 255, 255, 0.02);
  border-radius: 16px;
  border-left: 4px solid var(--electric-cyan);
  transition: all 0.3s ease;
}

.architecture-layer:hover {
  background: rgba(255, 255, 255, 0.05);
  transform: translateX(10px);
}

.layer-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.layer-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, var(--neon-blue), var(--electric-cyan));
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: white;
}

.layer-info {
  flex: 1;
}

.layer-name {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--pure-white);
  margin-bottom: 0.25rem;
}

.layer-tech {
  color: var(--electric-cyan);
  font-weight: 500;
  font-size: 0.875rem;
}

.layer-badge {
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
}

.layer-badge.production {
  background: rgba(16, 185, 129, 0.2);
  color: var(--emerald-pulse);
}

.layer-badge.beta {
  background: rgba(245, 158, 11, 0.2);
  color: var(--amber-glow);
}

.layer-badge.development {
  background: rgba(59, 130, 246, 0.2);
  color: var(--neon-blue);
}

.layer-badge.planned {
  background: rgba(139, 92, 246, 0.2);
  color: #8b5cf6;
}

.layer-badge.prototype {
  background: rgba(245, 158, 11, 0.2);
  color: var(--amber-glow);
}

.layer-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.layer-features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin-bottom: 2rem;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--steel-gray);
  font-size: 0.875rem;
}

.feature-item i {
  color: var(--emerald-pulse);
}

.layer-performance {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.performance-metric {
  text-align: center;
  min-width: 120px;
}

.metric-value {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--electric-cyan);
}

.metric-label {
  font-size: 0.75rem;
  color: var(--steel-gray);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.performance-bar {
  flex: 1;
  height: 8px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
  overflow: hidden;
}

.performance-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--electric-cyan), var(--neon-blue));
  border-radius: 4px;
  transition: width 1s ease;
}

.tech-stack-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.tech-category {
  padding: 2rem;
  background: rgba(255, 255, 255, 0.02);
  border-radius: 16px;
}

.category-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 2rem;
}

.category-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--pure-white);
}

.technologies-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.tech-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  transition: all 0.3s ease;
}

.tech-item:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateX(5px);
}

.tech-logo {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  color: var(--electric-cyan);
}

.tech-info {
  flex: 1;
}

.tech-name {
  font-weight: 600;
  color: var(--pure-white);
  margin-bottom: 0.25rem;
}

.tech-purpose {
  font-size: 0.875rem;
  color: var(--steel-gray);
}

.tech-rating {
  text-align: center;
}

.rating-stars {
  color: var(--amber-glow);
  font-size: 0.75rem;
  margin-bottom: 0.25rem;
}

.rating-text {
  font-size: 0.75rem;
  color: var(--steel-gray);
}

.performance-section {
  text-align: center;
}

.performance-title {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 3rem;
  color: var(--pure-white);
}

.metrics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.metric-card {
  padding: 2rem;
  text-align: center;
}

.metric-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  color: white;
  margin: 0 auto 1.5rem;
}

.metric-value {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, var(--electric-cyan), var(--neon-blue));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.metric-label {
  color: var(--steel-gray);
  margin-bottom: 1rem;
  font-weight: 500;
}

.metric-trend {
  font-size: 0.875rem;
  font-weight: 600;
}

.metric-trend.positive {
  color: var(--emerald-pulse);
}

.metric-trend.stable {
  color: var(--steel-gray);
}

@media (max-width: 768px) {
  .architecture-overview {
    padding: 2rem;
  }
  
  .layer-header {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }
  
  .tech-stack-grid {
    grid-template-columns: 1fr;
  }
  
  .metrics-grid {
    grid-template-columns: 1fr;
  }
}
</style>