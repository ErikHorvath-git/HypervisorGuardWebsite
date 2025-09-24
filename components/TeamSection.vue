<template>
  <section id="team" class="team-section section-spacing">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header">
        <div class="section-badge">MEET THE VISIONARIES</div>
        <h2 class="section-title gradient-text-emerald">
          Our Expert Team
        </h2>
        <p class="section-description body-large">
          Industry veterans and AI pioneers with decades of experience in enterprise 
          virtualization and machine learning.
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
        <h3 class="advisory-title">Advisory Board</h3>
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
          name: 'Dr. Sarah Chen',
          role: 'Chief AI Scientist',
          bio: 'PhD in Machine Learning from Stanford, former Google AI researcher with 12+ years in predictive analytics and neural networks.',
          expertise: ['Machine Learning', 'Neural Networks', 'Predictive Analytics', 'TensorFlow'],
          avatarColor: 'linear-gradient(135deg, #00f5d4, #0066ff)',
          avatarIcon: 'fas fa-brain',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'twitter', icon: 'fab fa-twitter', url: '#' },
            { platform: 'github', icon: 'fab fa-github', url: '#' }
          ]
        },
        {
          id: 2,
          name: 'Michael Rodriguez',
          role: 'Chief Technology Officer',
          bio: '15 years in enterprise virtualization, VMware certified architect, and cloud infrastructure expert. Led teams at AWS and Microsoft.',
          expertise: ['Virtualization', 'Cloud Architecture', 'Kubernetes', 'DevOps'],
          avatarColor: 'linear-gradient(135deg, #f59e0b, #f43f5e)',
          avatarIcon: 'fas fa-code',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'twitter', icon: 'fab fa-twitter', url: '#' }
          ]
        },
        {
          id: 3,
          name: 'Emily Watson',
          role: 'Chief Product Officer',
          bio: 'Product management veteran with successful exits in enterprise SaaS. Former Product Lead at Salesforce and Slack.',
          expertise: ['Product Strategy', 'SaaS', 'Enterprise Sales', 'UX Design'],
          avatarColor: 'linear-gradient(135deg, #10b981, #00f5d4)',
          avatarIcon: 'fas fa-chart-line',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'twitter', icon: 'fab fa-twitter', url: '#' }
          ]
        },
        {
          id: 4,
          name: 'David Kim',
          role: 'Head of Engineering',
          bio: 'Full-stack architect specializing in real-time data processing and scalable system design. Built systems handling 10M+ concurrent users.',
          expertise: ['Real-time Systems', 'Microservices', 'Vue.js', 'Apache Flink'],
          avatarColor: 'linear-gradient(135deg, #0066ff, #8b5cf6)',
          avatarIcon: 'fas fa-cogs',
          social: [
            { platform: 'linkedin', icon: 'fab fa-linkedin', url: '#' },
            { platform: 'github', icon: 'fab fa-github', url: '#' }
          ]
        }
      ],
      advisors: [
        {
          id: 1,
          name: 'Dr. James Wilson',
          company: 'Former CTO, VMware',
          role: 'Virtualization Expert',
          icon: 'fas fa-cloud'
        },
        {
          id: 2,
          name: 'Lisa Thompson',
          company: 'Partner, Sequoia Capital',
          role: 'Investment Strategy',
          icon: 'fas fa-chart-bar'
        },
        {
          id: 3,
          name: 'Robert Chen',
          company: 'Ex-Google AI',
          role: 'AI Research',
          icon: 'fas fa-robot'
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
}

.advisory-title {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 3rem;
  color: var(--pure-white);
}

.advisory-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  max-width: 800px;
  margin: 0 auto;
}

.advisor-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.02);
  border-radius: 15px;
  text-align: left;
}

.advisor-avatar {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--neon-blue), var(--electric-cyan));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: white;
  flex-shrink: 0;
}

.advisor-info {
  flex: 1;
}

.advisor-name {
  font-weight: 600;
  color: var(--pure-white);
  margin-bottom: 0.25rem;
}

.advisor-company {
  color: var(--electric-cyan);
  font-size: 0.875rem;
  font-weight: 500;
  margin-bottom: 0.25rem;
}

.advisor-role {
  color: var(--steel-gray);
  font-size: 0.75rem;
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
}
</style>