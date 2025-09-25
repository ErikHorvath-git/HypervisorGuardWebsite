<template>
  <footer class="professional-footer">
    <!-- CTA Section -->
    <div class="footer-cta">
      <div class="container">
        <div class="cta-content">
          <h2 class="cta-title gradient-text-cyan">
            Ready to Secure Critical Infrastructure?
          </h2>
          <p class="cta-description">
            Join the movement for European digital sovereignty. Contact us for technical collaboration, 
            pilot deployments, or investment in next-generation APT protection.
          </p>
          <div class="cta-actions">
            <button class="btn-primary btn-xl">
              <i class="fas fa-shield-alt mr-3"></i>
              Technical Demo
            </button>
            <button class="btn-secondary btn-xl">
              <i class="fas fa-file-contract mr-3"></i>
              Project Proposal
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Main Footer -->
    <div class="footer-main">
      <div class="container">
        <div class="footer-content">
          <!-- Project Info -->
          <div class="footer-section">
            <div class="footer-logo">
              <div class="logo-icon icon-container icon-md icon-cyan">
                <i class="fas fa-shield-alt"></i>
              </div>
              <span class="logo-text gradient-text-cyan">AI RAM Analyzer</span>
            </div>
            <p class="company-description">
              European sovereign security solution for critical infrastructure protection. 
              Hypervisor-powered APT detection with complete data sovereignty and zero cloud dependency.
            </p>
            <div class="social-links">
              <a v-for="social in socialLinks" :key="social.name" :href="social.url" class="social-link">
                <i :class="social.icon"></i>
              </a>
            </div>
          </div>

          <!-- Technology Links -->
          <div class="footer-section">
            <h3 class="footer-title">Technology</h3>
            <ul class="footer-links">
              <li v-for="link in technologyLinks" :key="link.name">
                <a :href="link.url" class="footer-link">
                  <i class="fas fa-chevron-right"></i>
                  {{ link.name }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Project Links -->
          <div class="footer-section">
            <h3 class="footer-title">Project</h3>
            <ul class="footer-links">
              <li v-for="link in projectLinks" :key="link.name">
                <a :href="link.url" class="footer-link">
                  <i class="fas fa-chevron-right"></i>
                  {{ link.name }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Contact Info -->
          <div class="footer-section">
            <h3 class="footer-title">Contact</h3>
            <div class="contact-info">
              <div v-for="contact in contactInfo" :key="contact.type" class="contact-item">
                <div class="contact-icon">
                  <i :class="contact.icon"></i>
                </div>
                <div class="contact-details">
                  <div class="contact-type">{{ contact.type }}</div>
                  <div class="contact-value">{{ contact.value }}</div>
                </div>
              </div>
            </div>
          </div>

          <!-- EU Initiatives -->
          <div class="footer-section">
            <h3 class="footer-title">EU Initiatives</h3>
            <p class="newsletter-description">
              Aligned with European digital sovereignty and critical infrastructure protection strategies.
            </p>
            <div class="initiatives-list">
              <div v-for="initiative in initiatives" :key="initiative" class="initiative-tag">
                <i class="fas fa-check"></i>
                {{ initiative }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer Bottom -->
    <div class="footer-bottom">
      <div class="container">
        <div class="footer-bottom-content">
          <div class="copyright">
            &copy; 2024 AI RAM Analyzer & Response Handler. European sovereign security solution.
          </div>
          <div class="footer-legal">
            <a v-for="link in legalLinks" :key="link.name" :href="link.url" class="legal-link">
              {{ link.name }}
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Decorative Elements -->
    <div class="footer-decoration"></div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      socialLinks: [
        { name: 'GitHub', icon: 'fab fa-github', url: '#' },
        { name: 'LinkedIn', icon: 'fab fa-linkedin', url: '#' },
        { name: 'Email', icon: 'fas fa-envelope', url: 'mailto:mailnavsetko206@gmail.com' }
      ],
      technologyLinks: [
        { name: 'Hypervisor Core', url: '#tech' },
        { name: 'AI Detection', url: '#tech' },
        { name: 'RAM Forensics', url: '#features' },
        { name: 'Response Engine', url: '#features' },
        { name: 'Architecture', url: '#tech' }
      ],
      projectLinks: [
        { name: 'Roadmap', url: '#roadmap' },
        { name: 'Team', url: '#team' },
        { name: 'Contact', url: '#contact' },
        { name: 'Open Source', url: '#' },
        { name: 'Documentation', url: '#' }
      ],
      contactInfo: [
        { type: 'Technical Lead', icon: 'fas fa-user-secret', value: 'Erik Horváth' },
        { type: 'Email', icon: 'fas fa-envelope', value: 'mailnavsetko206@gmail.com' },
        { type: 'Location', icon: 'fas fa-map-marker-alt', value: 'Nitra, Slovakia (EU)' }
      ],
      initiatives: [
        'NIS2 Directive',
        'GDPR Compliance', 
        'Digital Sovereignty',
        'Gaia-X Initiative'
      ],
      legalLinks: [
        { name: 'Privacy Policy', url: '#' },
        { name: 'Terms of Service', url: '#' },
        { name: 'Open Source License', url: '#' }
      ]
    }
  }
}
</script>

<style scoped>
.professional-footer {
  position: relative;
  background: linear-gradient(180deg, var(--deep-space) 0%, #0a0f1a 100%);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-cta {
  background: linear-gradient(135deg, rgba(0, 102, 255, 0.1) 0%, rgba(0, 245, 212, 0.1) 100%);
  padding: 6rem 0;
  text-align: center;
}

.cta-content {
  max-width: 800px;
  margin: 0 auto;
}

.cta-title {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.cta-description {
  font-size: 1.25rem;
  color: var(--steel-gray);
  margin-bottom: 3rem;
  line-height: 1.6;
}

.cta-actions {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

.btn-xl {
  padding: 1.25rem 2.5rem;
  font-size: 1.125rem;
}

.footer-main {
  padding: 6rem 0 3rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr 1.5fr;
  gap: 3rem;
}

.footer-section:first-child {
  grid-column: 1 / 2;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
}

.company-description {
  color: var(--steel-gray);
  line-height: 1.6;
  margin-bottom: 2rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 45px;
  height: 45px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--steel-gray);
  text-decoration: none;
  transition: all 0.3s ease;
  font-size: 1.25rem;
}

.social-link:hover {
  background: var(--electric-cyan);
  color: var(--deep-space);
  transform: translateY(-2px);
}

.footer-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  color: var(--pure-white);
}

.footer-links {
  list-style: none;
}

.footer-links li {
  margin-bottom: 0.75rem;
}

.footer-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--steel-gray);
  text-decoration: none;
  transition: all 0.3s ease;
}

.footer-link:hover {
  color: var(--electric-cyan);
  transform: translateX(5px);
}

.footer-link i {
  font-size: 0.75rem;
  color: var(--electric-cyan);
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.contact-icon {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--electric-cyan);
}

.contact-details {
  flex: 1;
}

.contact-type {
  font-size: 0.875rem;
  color: var(--steel-gray);
  margin-bottom: 0.25rem;
}

.contact-value {
  font-weight: 500;
  color: var(--pure-white);
}

.newsletter-description {
  color: var(--steel-gray);
  margin-bottom: 1.5rem;
  line-height: 1.5;
}

.initiatives-list {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.initiative-tag {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--steel-gray);
  font-size: 0.875rem;
}

.initiative-tag i {
  color: var(--emerald-pulse);
  font-size: 0.75rem;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 2rem 0;
}

.footer-bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.copyright {
  color: var(--steel-gray);
  font-size: 0.875rem;
}

.footer-legal {
  display: flex;
  gap: 2rem;
}

.legal-link {
  color: var(--steel-gray);
  text-decoration: none;
  font-size: 0.875rem;
  transition: color 0.3s ease;
}

.legal-link:hover {
  color: var(--electric-cyan);
}

.footer-decoration {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--electric-cyan), transparent);
}

@media (max-width: 1024px) {
  .footer-content {
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
  
  .footer-section:first-child {
    grid-column: 1 / -1;
    text-align: center;
  }
  
  .footer-logo {
    justify-content: center;
  }
  
  .social-links {
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .footer-cta {
    padding: 4rem 0;
  }
  
  .cta-title {
    font-size: 2rem;
  }
  
  .cta-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .footer-bottom-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
  
  .footer-legal {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>