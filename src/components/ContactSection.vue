<template>
  <section id="contact" class="contact-section section-spacing">
    <div class="container">
      <div class="section-header">
        <div class="section-badge">CONTACT & PARTNERSHIPS</div>
        <h2 class="section-title gradient-text-cyan">
          Interested in European Security Sovereignty?
        </h2>
        <p class="section-description body-large">
          Contact us for technical collaboration, pilot deployments, or investment in EU-based critical infrastructure protection.
        </p>
      </div>

      <div class="contact-content">
        <div class="contact-info">
          <div v-for="contact in contacts" :key="contact.id" class="contact-card glass-morphism hover-3d">
            <div class="contact-icon icon-container icon-lg icon-cyan">
              <i :class="contact.icon"></i>
            </div>
            <h3 class="contact-type">{{ contact.type }}</h3>
            <div class="contact-value">{{ contact.value }}</div>
            <p class="contact-description">{{ contact.description }}</p>
            <button class="contact-action">{{ contact.actionText }}</button>
          </div>
        </div>

        <!-- Additional Info -->
        <div class="additional-info glass-morphism">
          <h3>Project Details</h3>
          <div class="info-grid">
            <div class="info-item">
              <i class="fas fa-map-marker-alt"></i>
              <div>
                <strong>Location:</strong>
                <span>Nitra, Slovakia (EU)</span>
              </div>
            </div>
          <!--   
            <div class="info-item">
              <i class="fas fa-graduation-cap"></i>
              <div>
                <strong>Academic Base:</strong>
                <span>University of Constantine the Philosopher</span>
              </div>
            </div>
          -->  
            <div class="info-item">
              <i class="fas fa-shield-alt"></i>
              <div>
                <strong>Focus:</strong>
                <span>Critical Infrastructure Protection</span>
              </div>
            </div>
            <div class="info-item">
              <i class="fas fa-code-branch"></i>
              <div>
                <strong>Status:</strong>
                <span>Active Development (TRL 2-3)</span>
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
  name: 'ContactSection',
  data() {
    return {
      contacts: [
        {
          id: 1,
          type: 'Technical Collaboration',
          value: 'erik.horvathlab@proton.me',
          description: 'For technical discussions, code review, or development partnerships',
          icon: 'fas fa-code',
          actionText: 'Email Technical Lead'
        },
        {
          id: 2,
          type: 'Pilot Deployment',
          value: 'erik.horvathlab@proton.me',
          description: 'Organizations interested in pilot testing for critical infrastructure',
          icon: 'fas fa-rocket',
          actionText: 'Discuss Pilot'
        },
        {
          id: 3,
          type: 'Investment & Grants',
          value: 'erik.horvathlab@proton.me',
          description: 'EU funding opportunities, grants, or strategic investment',
          icon: 'fas fa-handshake',
          actionText: 'Explore Funding'
        }
      ]
    }
  }
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.8) 0%, var(--deep-space) 100%);
}

.contact-content {
  max-width: 1000px;
  margin: 0 auto;
}

.contact-info {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.contact-card {
  padding: 2.5rem;
  text-align: center;
}

.contact-type {
  font-size: 1.25rem;
  font-weight: 600;
  margin: 1rem 0 0.5rem;
  color: var(--pure-white);
}

.contact-value {
  color: var(--electric-cyan);
  font-weight: 500;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.contact-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.5;
  font-size: 0.9rem;
}

.contact-action {
  background: var(--electric-cyan);
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  color: var(--deep-space);
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 100%;
}

.contact-action:hover {
  transform: translateY(-2px);
}

.additional-info {
  padding: 2rem;
  border-radius: 15px;
}

.additional-info h3 {
  color: var(--pure-white);
  margin-bottom: 1.5rem;
  text-align: center;
  font-size: 1.5rem;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.info-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
}

.info-item i {
  color: var(--electric-cyan);
  font-size: 1.25rem;
  width: 30px;
}

.info-item div {
  display: flex;
  flex-direction: column;
}

.info-item strong {
  color: var(--pure-white);
  font-size: 0.9rem;
}

.info-item span {
  color: var(--steel-gray);
  font-size: 0.85rem;
}

@media (max-width: 768px) {
  .contact-info {
    grid-template-columns: 1fr;
  }
  
  .info-grid {
    grid-template-columns: 1fr;
  }
  
  .info-item {
    flex-direction: column;
    text-align: center;
    gap: 0.5rem;
  }
}
</style>