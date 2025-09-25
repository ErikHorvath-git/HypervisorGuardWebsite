<template>
  <section id="roadmap" class="roadmap-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">DEVELOPMENT PHASES</div>
        <h2 class="section-title gradient-text-amber">
          Project Roadmap
        </h2>
        <p class="section-description body-large">
          Strategic development plan for hypervisor-based APT detection and response system.
        </p>
      </div>

      <!-- Timeline -->
      <div class="timeline">
        <div v-for="phase in roadmap" :key="phase.id" class="timeline-phase" :class="phase.status">
          <div class="phase-marker">
            <div class="marker-icon">
              <i :class="phase.icon"></i>
            </div>
            <div class="marker-line"></div>
          </div>
          
          <div class="phase-content glass-morphism hover-3d">
            <div class="phase-header">
              <span class="phase-badge" :class="phase.status">{{ phase.status }}</span>
              <span class="phase-date">{{ phase.month }}</span>
            </div>
            
            <h3 class="phase-title">{{ phase.title }}</h3>
            <p class="phase-description">{{ phase.description }}</p>
            
            <div class="phase-features">
              <div v-for="feature in phase.features" :key="feature" class="feature-tag">
                {{ feature }}
              </div>
            </div>
            
            <div class="phase-progress" v-if="phase.progress">
              <div class="progress-bar">
                <div class="progress-fill" :style="{ width: phase.progress + '%' }"></div>
              </div>
              <span class="progress-text">{{ phase.progress }}% Complete</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Roadmap',
  data() {
    return {
      roadmap: [
        {
          id: 1,
          month: 'M0',
          status: 'completed',
          icon: 'fas fa-flask',
          title: 'Proof of Concept',
          description: 'User-space PoC with mock AI engine and basic pipeline for RAM dump analysis.',
          features: ['User-space prototype', 'Mock AI detection', 'Basic pipeline', 'Manual testing'],
          progress: 100
        },
        {
          id: 2,
          month: 'M1-M2',
          status: 'in-progress',
          icon: 'fas fa-shield-alt',
          title: 'Hypervisor Core',
          description: 'Stable minimal hypervisor with VMX initialization, VMCS management and EPT mapping.',
          features: ['VMX on/off', 'VMCS life-cycle', 'EPT identity map', 'MSR/CR trapping'],
          progress: 60
        },
        {
          id: 3,
          month: 'M2-M3',
          status: 'upcoming',
          icon: 'fas fa-memory',
          title: 'RAM Acquisition',
          description: 'Secure memory collection with DMA-safe dumping and process mapping capabilities.',
          features: ['DMA-safe RAM snapshot', 'CR3 monitoring', 'Process mapping', 'Hidden module detection'],
          progress: 0
        },
        {
          id: 4,
          month: 'M3-M4',
          status: 'upcoming',
          icon: 'fas fa-brain',
          title: 'AI Detection Engine',
          description: 'Production AI detector replacing mock engine with advanced threat detection capabilities.',
          features: ['Feature extraction', 'ML model training', 'YARA rules', 'Heuristic analysis'],
          progress: 0
        },
        {
          id: 5,
          month: 'M4-M5',
          status: 'planned',
          icon: 'fas fa-bolt',
          title: 'Response & Containment',
          description: 'Real-time threat response with automated containment and rollback capabilities.',
          features: ['Thread suspension', 'EPT revocation', 'Syscall blocking', 'Snapshot rollback'],
          progress: 0
        },
        {
          id: 6,
          month: 'M5',
          status: 'planned',
          icon: 'fas fa-lock',
          title: 'Hardening & Stealth',
          description: 'Anti-tamper protection and resilience against bypass techniques.',
          features: ['VMCS protection', 'Anti-debug measures', 'Integrity checks', 'TPM integration'],
          progress: 0
        },
        {
          id: 7,
          month: 'M6',
          status: 'planned',
          icon: 'fas fa-rocket',
          title: 'Pilot Deployment',
          description: 'Production-ready deployment with partner integration and enterprise features.',
          features: ['SIEM integration', 'Admin GUI', 'Pilot deployment', 'SLA compliance'],
          progress: 0
        }
      ]
    }
  }
}
</script>

<style scoped>
.roadmap-section {
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.8) 0%, var(--deep-space) 100%);
}

.timeline {
  position: relative;
  max-width: 1000px;
  margin: 0 auto;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 60px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, var(--electric-cyan), var(--amber-glow));
}

.timeline-phase {
  display: flex;
  gap: 2rem;
  margin-bottom: 4rem;
  position: relative;
}

.phase-marker {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 120px;
  flex-shrink: 0;
}

.marker-icon {
  width: 60px;
  height: 60px;
  background: var(--space-gray);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  z-index: 2;
}

.timeline-phase.completed .marker-icon {
  background: var(--emerald-pulse);
  color: white;
}

.timeline-phase.in-progress .marker-icon {
  background: var(--amber-glow);
  color: white;
  animation: pulse 2s infinite;
}

.timeline-phase.upcoming .marker-icon {
  background: var(--neon-blue);
  color: white;
}

.timeline-phase.planned .marker-icon {
  background: var(--steel-gray);
  color: white;
}

.marker-line {
  flex: 1;
  width: 2px;
  background: var(--steel-gray);
  margin: 1rem 0;
}

.phase-content {
  flex: 1;
  padding: 2.5rem;
  margin-bottom: 2rem;
}

.phase-header {
  display: flex;
  justify-content: between;
  align-items: center;
  margin-bottom: 1rem;
  gap: 1rem;
}

.phase-badge {
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.phase-badge.completed {
  background: rgba(16, 185, 129, 0.2);
  color: var(--emerald-pulse);
}

.phase-badge.in-progress {
  background: rgba(245, 158, 11, 0.2);
  color: var(--amber-glow);
}

.phase-badge.upcoming {
  background: rgba(0, 102, 255, 0.2);
  color: var(--neon-blue);
}

.phase-badge.planned {
  background: rgba(100, 116, 139, 0.2);
  color: var(--steel-gray);
}

.phase-date {
  color: var(--steel-gray);
  font-weight: 600;
}

.phase-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--pure-white);
}

.phase-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.phase-features {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 2rem;
}

.feature-tag {
  background: rgba(255, 255, 255, 0.05);
  padding: 0.5rem 1rem;
  border-radius: 15px;
  font-size: 0.875rem;
  color: var(--steel-gray);
}

.phase-progress {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.progress-bar {
  flex: 1;
  height: 6px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 3px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--electric-cyan), var(--neon-blue));
  border-radius: 3px;
  transition: width 1s ease;
}

.progress-text {
  font-size: 0.875rem;
  color: var(--steel-gray);
  font-weight: 600;
  min-width: 100px;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.1); }
}

@media (max-width: 768px) {
  .timeline::before {
    left: 30px;
  }
  
  .timeline-phase {
    flex-direction: column;
    gap: 1rem;
  }
  
  .phase-marker {
    flex-direction: row;
    width: 100%;
    align-items: center;
  }
  
  .marker-line {
    flex: 1;
    height: 2px;
    width: auto;
    margin: 0 1rem;
  }
  
  .phase-content {
    margin-left: 0;
  }
}
</style>