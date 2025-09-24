<template>
  <section id="contact" class="contact-section section-spacing">
    <div class="container">
      <div class="section-header">
        <div class="section-badge">GET IN TOUCH</div>
        <h2 class="section-title gradient-text-cyan">
          Ready to Transform Your Infrastructure?
        </h2>
        <p class="section-description body-large">
          Contact our team to schedule a demo or learn more about investment opportunities.
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
            <button class="contact-action">Contact Us</button>
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
          type: 'Sales Demo',
          value: 'demo@hypervisor-ai.com',
          icon: 'fas fa-calendar-check'
        },
        {
          id: 2,
          type: 'Investor Relations',
          value: 'investors@hypervisor-ai.com',
          icon: 'fas fa-chart-line'
        },
        {
          id: 3,
          type: 'Technical Support',
          value: 'support@hypervisor-ai.com',
          icon: 'fas fa-headset'
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
  margin-bottom: 1.5rem;
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
}

.contact-action:hover {
  transform: translateY(-2px);
}
</style>