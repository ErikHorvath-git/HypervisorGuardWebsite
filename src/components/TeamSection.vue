<template>
  <section id="team" class="team-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">OUR TEAM</div>
        <h2 class="section-title gradient-text-emerald">
          Core Team & Advisors
        </h2>
        <p class="section-description body-large">
          Passionate cybersecurity experts and AI developers focused on creating 
          European sovereign security solutions for critical infrastructure.
        </p>
      </div>

      <!-- Team Grid -->
      <div class="team-grid">
        <div v-for="member in team" :key="member.id" class="team-card glass-morphism hover-3d">
          <div class="member-avatar">
            <div class="avatar-image" :style="{ background: member.avatarColor }">
              <i :class="member.avatarIcon"></i>
            </div>
            <div class="avatar-decoration"></div>
          </div>
          
          <div class="member-info">
            <h3 class="member-name">{{ member.name }}</h3>
            <div class="member-role gradient-text-cyan">{{ member.role }}</div>
            <p class="member-bio">{{ member.bio }}</p>
            
            <div class="member-expertise">
              <span v-for="skill in member.expertise" :key="skill" class="expertise-tag">
                {{ skill }}
              </span>
            </div>
            
            <div class="member-social">
              <a v-for="social in member.social" :key="social.platform" :href="social.url" class="social-link">
                <i :class="social.icon"></i>
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Advisory Board -->
      <div class="advisory-section">
        <h3 class="advisory-title">Security Advisors</h3>
        <div class="advisory-grid">
          <div v-for="advisor in advisors" :key="advisor.id" class="advisor-card">
            <div class="advisor-avatar">
              <i :class="advisor.icon"></i>
            </div>
            <div class="advisor-info">
              <h4 class="advisor-name">{{ advisor.name }}</h4>
              <div class="advisor-company">{{ advisor.company }}</div>
              <div class="advisor-role">{{ advisor.role }}</div>
            </div>
          </div>
        </div>
      </div>

      <!-- Hiring Section -->
      <div class="hiring-section glass-morphism">
        <h3 class="hiring-title">We're Hiring Key Roles</h3>
        <div class="hiring-grid">
          <div v-for="position in hiring" :key="position.id" class="position-card">
            <div class="position-icon" :style="{ background: position.color }">
              <i :class="position.icon"></i>
            </div>
            <h4 class="position-title">{{ position.title }}</h4>
            <p class="position-description">{{ position.description }}</p>
            <div class="position-requirements">
              <span v-for="req in position.requirements" :key="req" class="requirement-tag">
                {{ req }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TeamSection',
  data() {
    return {
      team: [
        {
          id: 1,
          name: 'Erik Horváth',
          role: 'Founder & Lead Developer',
          bio: 'Cybersecurity enthusiast and Applied Informatics student with focus on low-level security solutions, hypervisor technology, and AI-powered threat detection.',
          expertise: ['C/C++', 'Python', 'Linux', 'Hypervisor Tech', 'AI Security', 'RAM Forensics'],
          avatarColor: 'linear-gradient(135deg, #00f5d4, #0066ff)',
          avatarIcon: 'fas fa-user-secret',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'github', icon: 'fab fa-github', url: '#' }
          ]
        },
        {
          id: 2,
          name: 'AI Engineer',
          role: 'Senior AI/ML Specialist',
          bio: 'Position to be filled - seeking expert in machine learning for security anomaly detection and behavioral analysis.',
          expertise: ['Machine Learning', 'Python', 'TensorFlow/PyTorch', 'Security Analytics', 'YARA'],
          avatarColor: 'linear-gradient(135deg, #f59e0b, #f43f5e)',
          avatarIcon: 'fas fa-robot',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'github', icon: 'fab fa-github', url: '#' }
          ]
        },
        {
          id: 3,
          name: 'Low-Level Programmer',
          role: 'OS Architecture Expert',
          bio: 'Position to be filled - seeking developer with deep expertise in kernel development, hypervisors, and low-level system programming.',
          expertise: ['C/C++', 'Assembly', 'Windows/Linux Kernel', 'VMX/AMD-V', 'Driver Development'],
          avatarColor: 'linear-gradient(135deg, #10b981, #00f5d4)',
          avatarIcon: 'fas fa-microchip',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'github', icon: 'fab fa-github', url: '#' }
          ]
        }
      ],
      advisors: [
        {
          id: 1,
          name: 'Industry Experts',
          company: 'Cybersecurity Community',
          role: 'Technical Consultation',
          icon: 'fas fa-users'
        }
      ],
      hiring: [
        {
          id: 1,
          title: 'AI Engineer (Mid-Senior)',
          description: 'Develop and optimize ML models for APT detection and behavioral analysis.',
          requirements: ['Python', 'TensorFlow/PyTorch', 'Security Analytics', 'MLOps'],
          icon: 'fas fa-brain',
          color: 'linear-gradient(135deg, #00f5d4, #0066ff)'
        },
        {
          id: 2,
          title: 'Low-Level Programmer',
          description: 'Hypervisor development, kernel modules, and system architecture.',
          requirements: ['C/C++', 'Assembly', 'VMX/AMD-V', 'Driver Development'],
          icon: 'fas fa-code',
          color: 'linear-gradient(135deg, #f59e0b, #f43f5e)'
        },
        {
          id: 3,
          title: 'Product Owner',
          description: 'Lead product strategy and coordinate development with security focus.',
          requirements: ['Cybersecurity', 'Product Management', 'Critical Infrastructure'],
          icon: 'fas fa-chart-line',
          color: 'linear-gradient(135deg, #10b981, #00f5d4)'
        }
      ]
    }
  }
}
</script>

<style scoped>
.team-section {
  background: linear-gradient(180deg, var(--deep-space) 0%, rgba(15, 23, 42, 0.9) 100%);
}

.gradient-text-emerald {
  background: linear-gradient(135deg, var(--emerald-pulse) 0%, var(--electric-cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 6rem;
}

.team-card {
  padding: 2.5rem;
  text-align: center;
}

.member-avatar {
  position: relative;
  display: inline-block;
  margin-bottom: 2rem;
}

.avatar-image {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  color: white;
  position: relative;
  z-index: 2;
}

.avatar-decoration {
  position: absolute;
  top: -10px;
  left: -10px;
  right: -10px;
  bottom: -10px;
  background: conic-gradient(from 0deg, var(--electric-cyan), var(--neon-blue), var(--amber-glow), var(--electric-cyan));
  border-radius: 50%;
  animation: rotate 10s linear infinite;
  opacity: 0.3;
}

.member-name {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--pure-white);
}

.member-role {
  font-size: 1.125rem;
  font-weight: 500;
  margin-bottom: 1rem;
}

.member-bio {
  color: var(--steel-gray);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.member-expertise {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
  margin-bottom: 2rem;
}

.expertise-tag {
  background: rgba(255, 255, 255, 0.05);
  padding: 0.5rem 1rem;
  border-radius: 15px;
  font-size: 0.75rem;
  color: var(--steel-gray);
  font-weight: 500;
}

.member-social {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.social-link {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--steel-gray);
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: var(--electric-cyan);
  color: var(--deep-space);
  transform: translateY(-2px);
}

.advisory-section {
  text-align: center;
  margin-bottom: 4rem;
}

.advisory-title {
  font-size: 1.5rem; /* Reduced from 2rem */
  font-weight: 600;
  margin-bottom: 2rem; /* Reduced from 3rem */
  color: var(--pure-white);
}

.advisory-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Reduced min width */
  gap: 1rem; /* Reduced from 2rem */
  max-width: 600px; /* Reduced from 800px */
  margin: 0 auto;
}

.advisor-card {
  display: flex;
  align-items: center;
  gap: 0.75rem; /* Reduced from 1rem */
  padding: 1rem; /* Reduced from 1.5rem */
  background: rgba(255, 255, 255, 0.02);
  border-radius: 12px; /* Slightly smaller radius */
  text-align: left;
  min-height: auto; /* Remove any fixed height */
}

.advisor-avatar {
  width: 50px; /* Reduced from 60px */
  height: 50px; /* Reduced from 60px */
  background: linear-gradient(135deg, var(--neon-blue), var(--electric-cyan));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem; /* Reduced from 1.5rem */
  color: white;
  flex-shrink: 0;
}

.advisor-info {
  flex: 1;
  min-width: 0; /* Prevent text overflow */
}

.advisor-name {
  font-weight: 600;
  color: var(--pure-white);
  margin-bottom: 0.2rem; /* Reduced spacing */
  font-size: 0.9rem; /* Slightly smaller text */
  line-height: 1.2;
}

.advisor-company {
  color: var(--electric-cyan);
  font-size: 0.75rem; /* Reduced from 0.875rem */
  font-weight: 500;
  margin-bottom: 0.2rem; /* Reduced spacing */
  line-height: 1.2;
}

.advisor-role {
  color: var(--steel-gray);
  font-size: 0.7rem; /* Reduced from 0.75rem */
  line-height: 1.2;
}

.hiring-section {
  padding: 3rem;
  text-align: center;
}

.hiring-title {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 3rem;
  color: var(--pure-white);
}

.hiring-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.position-card {
  padding: 2rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 15px;
  text-align: center;
}

.position-icon {
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

.position-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--pure-white);
}

.position-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.5;
}

.position-requirements {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
}

.requirement-tag {
  background: rgba(255, 255, 255, 0.1);
  padding: 0.5rem 1rem;
  border-radius: 15px;
  font-size: 0.75rem;
  color: var(--steel-gray);
  font-weight: 500;
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@media (max-width: 768px) {
  .team-grid {
    grid-template-columns: 1fr;
  }
  
  .advisor-card {
    flex-direction: column;
    text-align: center;
  }
  
  .hiring-grid {
    grid-template-columns: 1fr;
  }
}
</style>