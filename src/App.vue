<script setup>
import { computed, ref, onMounted } from "vue";

import logo from "./assets/projects/DPBC+Ltd+logo-41e256d3.png";
import labc from "./assets/projects/LABC.png";
import heroImage from "./assets/projects/IMG_0075.JPEG";
import projectA from "./assets/projects/IMG_0051.jpg";
import projectB from "./assets/projects/IMG_0060.JPEG";
import projectC from "./assets/projects/IMG_0068.JPEG";
import projectD from "./assets/projects/IMG_0070.JPEG";
import projectE from "./assets/projects/Kitchen+4.jpg";
import projectF from "./assets/projects/Loft+Conversion+(2).jpg";
import projectG from "./assets/projects/IMGP0747.JPG";
import beforeImage from "./assets/projects/IMG_1559.JPG";
import afterImage from "./assets/projects/IMG_2276.JPG";

const reveal = ref(50);
const revealStyle = computed(() => ({ clipPath: `inset(0 ${100 - reveal.value}% 0 0)` }));

const mobileMenuOpen = ref(false);
const scrolled = ref(false);

onMounted(() => {
  window.addEventListener('scroll', () => {
    scrolled.value = window.scrollY > 50;
  });
});

const services = [
  { name: "Extensions", desc: "Single, two-storey, side, and wrap-around" },
  { name: "Loft Conversions", desc: "Creating additional living space" },
  { name: "Barn Conversions", desc: "Sympathetic restoration projects" },
  { name: "Renovations", desc: "Complete property refurbishment" },
  { name: "Fitted Kitchens", desc: "Custom design and installation" },
  { name: "Fitted Bathrooms", desc: "Including wet rooms" },
  { name: "Garden Rooms", desc: "Oak-framed outdoor living" },
  { name: "Roofing", desc: "Repairs and full replacements" },
  { name: "Bespoke Joinery", desc: "Custom carpentry and woodwork" },
  { name: "Stone Masonry", desc: "Traditional stonework restoration" },
  { name: "Plumbing & Electrics", desc: "Full installation services" },
  { name: "Hard Landscaping", desc: "Groundworks and foundations" }
];

const projects = [
  { title: "Two Storey Extension", desc: "Garage demolition for family extension in Cheltenham", image: projectA, location: "Cheltenham", year: "2023" },
  { title: "Barn Conversion", desc: "Derelict cattle barn transformed into living accommodation", image: projectB, location: "Coaley", year: "2022" },
  { title: "Cottage Extension", desc: "Small cottage extended for extra living space", image: projectC, location: "Uley", year: "2023" },
  { title: "New Build Garage", desc: "Garage with storage room above", image: projectD, location: "Berkeley", year: "2022" },
  { title: "Fitted Kitchen", desc: "Complete kitchen supply and installation", image: projectE, location: "Uley", year: "2023" },
  { title: "Loft Conversion", desc: "Creating additional bedroom space", image: projectF, location: "Dursley", year: "2022" },
  { title: "Stone Masonry", desc: "Chimney rebuilding and restoration", image: projectG, location: "Uley", year: "2023" }
];

const credentials = [
  { stat: "58", label: "Years Established", sublabel: "Since 1966" },
  { stat: "500+", label: "Projects Completed", sublabel: "Across Gloucestershire" },
  { stat: "LABC", label: "Award Winner", sublabel: "Built-in Quality" }
];
</script>

<template>
  <div class="site">
    <!-- Navigation -->
    <nav class="nav" :class="{ scrolled }">
      <div class="nav-container">
        <a href="#top" class="nav-brand">
          <img :src="logo" alt="DPrice Builders" />
          <span class="brand-text">
            <strong>DPrice Builders</strong>
            <small>Est. 1966</small>
          </span>
        </a>

        <div class="nav-links" :class="{ open: mobileMenuOpen }">
          <a href="#heritage" @click="mobileMenuOpen = false">Heritage</a>
          <a href="#services" @click="mobileMenuOpen = false">Services</a>
          <a href="#portfolio" @click="mobileMenuOpen = false">Portfolio</a>
          <a href="#contact" @click="mobileMenuOpen = false">Contact</a>
          <a href="tel:07738664699" class="nav-phone">07738 664699</a>
        </div>

        <button class="nav-toggle" @click="mobileMenuOpen = !mobileMenuOpen" :aria-label="mobileMenuOpen ? 'Close menu' : 'Open menu'">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </nav>

    <!-- Hero Section -->
    <section id="top" class="hero">
      <div class="hero-bg">
        <img :src="heroImage" alt="Premium extension work by DPrice Builders" />
        <div class="hero-overlay"></div>
      </div>

      <div class="hero-content">
        <div class="hero-badge">
          <span class="badge-icon">◆</span>
          <span>Gloucestershire Building Contractors</span>
        </div>

        <h1 class="hero-title">
          <span class="title-line">Built to Last.</span>
          <span class="title-line">Crafted with Care.</span>
        </h1>

        <p class="hero-subtitle">
          For over five decades, DPrice Builders has transformed properties across Gloucestershire with precision, integrity, and unwavering commitment to quality craftsmanship.
        </p>

        <div class="hero-actions">
          <a href="tel:07738664699" class="btn btn-primary">
            <span>Call 07738 664699</span>
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path d="M4 4L16 16M16 16V6M16 16H6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
            </svg>
          </a>
          <a href="#portfolio" class="btn btn-secondary">View Our Work</a>
        </div>

        <div class="hero-credentials">
          <div v-for="cred in credentials" :key="cred.label" class="credential">
            <div class="credential-stat">{{ cred.stat }}</div>
            <div class="credential-label">{{ cred.label }}</div>
            <div class="credential-sub">{{ cred.sublabel }}</div>
          </div>
        </div>
      </div>

      <div class="hero-scroll">
        <span>Scroll to explore</span>
        <div class="scroll-line"></div>
      </div>
    </section>

    <!-- Heritage Section -->
    <section id="heritage" class="heritage">
      <div class="heritage-container">
        <div class="heritage-content">
          <div class="section-label">
            <span class="label-icon">◆</span>
            <span>Our Heritage</span>
          </div>

          <h2 class="section-title">Three Generations of Building Excellence</h2>

          <div class="heritage-story">
            <div class="story-block">
              <div class="year">1966</div>
              <h3>Founded by David Price</h3>
              <p>David Price established the company with a vision of delivering honest, quality building work to the people of Gloucestershire. From day one, the focus was on craftsmanship, reliability, and building lasting relationships with clients.</p>
            </div>

            <div class="story-block">
              <div class="year">1988</div>
              <h3>Jason Joins the Business</h3>
              <p>Jason Price, David's eldest son, joined the family business straight from school. He pursued professional qualifications, earning his City and Guilds in plumbing and heating, bringing both heritage and modern expertise to the company.</p>
            </div>

            <div class="story-block">
              <div class="year">Today</div>
              <h3>Led by Jason Price</h3>
              <p>Now under Jason's leadership, DPrice Builders continues the family tradition of excellence while embracing modern building techniques. We collaborate closely with structural engineers, architects, and building authorities to deliver projects that exceed expectations.</p>
            </div>
          </div>

          <div class="heritage-awards">
            <div class="award-card">
              <img :src="labc" alt="LABC Built-in Quality Award" />
              <div class="award-text">
                <h4>LABC Built-in Quality Award</h4>
                <p>Recognized for outstanding building standards and project management excellence across Gloucestershire.</p>
              </div>
            </div>

            <div class="certification">
              <div class="cert-badge">FMB</div>
              <div class="cert-text">
                <strong>Federation of Master Builders</strong>
                <p>Proud member ensuring highest industry standards</p>
              </div>
            </div>
          </div>
        </div>

        <div class="heritage-stats">
          <div class="stat-card">
            <div class="stat-number">58</div>
            <div class="stat-label">Years of Excellence</div>
          </div>
          <div class="stat-card">
            <div class="stat-number">500+</div>
            <div class="stat-label">Projects Completed</div>
          </div>
          <div class="stat-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Client Satisfaction</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="services-container">
        <div class="services-header">
          <div class="section-label">
            <span class="label-icon">◆</span>
            <span>Our Services</span>
          </div>
          <h2 class="section-title">Comprehensive Building Solutions</h2>
          <p class="services-intro">From initial consultation to final handover, we manage every aspect of your project with meticulous attention to detail. Our comprehensive services cover all residential building needs across Gloucestershire.</p>
        </div>

        <div class="services-grid">
          <div v-for="service in services" :key="service.name" class="service-card">
            <div class="service-icon">◆</div>
            <h3>{{ service.name }}</h3>
            <p>{{ service.desc }}</p>
          </div>
        </div>

        <div class="services-cta">
          <div class="cta-content">
            <h3>Not sure what you need?</h3>
            <p>We'll visit your property, discuss your vision, and provide honest, practical advice on the best approach for your project.</p>
          </div>
          <a href="tel:07738664699" class="btn btn-primary">Schedule a Consultation</a>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="portfolio">
      <div class="portfolio-container">
        <div class="portfolio-header">
          <div class="section-label">
            <span class="label-icon">◆</span>
            <span>Our Portfolio</span>
          </div>
          <h2 class="section-title">Recent Projects Across Gloucestershire</h2>
        </div>

        <div class="portfolio-grid">
          <article v-for="(project, idx) in projects" :key="project.title" class="project-card" :class="`project-${idx % 3}`">
            <div class="project-image">
              <img :src="project.image" :alt="project.title" loading="lazy" />
              <div class="project-overlay">
                <div class="project-meta">
                  <span class="project-location">{{ project.location }}</span>
                  <span class="project-year">{{ project.year }}</span>
                </div>
              </div>
            </div>
            <div class="project-info">
              <h3>{{ project.title }}</h3>
              <p>{{ project.desc }}</p>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- Before/After Section -->
    <section class="transformation">
      <div class="transformation-container">
        <div class="transformation-header">
          <div class="section-label light">
            <span class="label-icon">◆</span>
            <span>Transformation</span>
          </div>
          <h2 class="section-title light">See the Difference</h2>
          <p class="transformation-intro">Slide to reveal the transformation. Quality craftsmanship creates lasting value.</p>
        </div>

        <div class="comparison-slider">
          <div class="comparison-container">
            <img :src="beforeImage" alt="Before renovation" class="comparison-image" />
            <div class="comparison-overlay" :style="revealStyle">
              <img :src="afterImage" alt="After renovation" class="comparison-image" />
            </div>
            <div class="comparison-labels">
              <span class="label-before">Before</span>
              <span class="label-after">After</span>
            </div>
            <input
              v-model="reveal"
              type="range"
              min="0"
              max="100"
              class="comparison-range"
              aria-label="Slide to compare before and after"
            />
            <div class="comparison-handle" :style="{ left: reveal + '%' }">
              <div class="handle-line"></div>
              <div class="handle-circle">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M15 18L9 12L15 6" stroke="currentColor" stroke-width="2"/>
                  <path d="M9 18L15 12L9 6" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
      <div class="contact-container">
        <div class="contact-content">
          <div class="section-label">
            <span class="label-icon">◆</span>
            <span>Get in Touch</span>
          </div>

          <h2 class="section-title">Let's Discuss Your Project</h2>

          <p class="contact-intro">Whether you have detailed plans or just an initial idea, we're here to help. Get in touch for a free consultation and discover how we can bring your vision to life.</p>

          <div class="contact-methods">
            <a href="tel:07738664699" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M22 16.92V19.92C22 20.47 21.54 20.93 20.99 20.92C10.94 20.45 3 12.51 2.53 2.46C2.52 1.91 2.98 1.45 3.53 1.45H6.53C7.08 1.45 7.54 1.91 7.54 2.46C7.54 3.56 7.74 4.61 8.11 5.59C8.22 5.87 8.15 6.19 7.93 6.41L6.21 8.13C7.87 11.57 10.88 14.58 14.32 16.24L16.04 14.52C16.26 14.3 16.58 14.23 16.86 14.34C17.84 14.71 18.89 14.91 19.99 14.91C20.54 14.91 21 15.37 21 15.92V18.92C21 19.47 20.54 19.93 19.99 19.92Z" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <div class="method-text">
                <strong>Call Us</strong>
                <span>07738 664699</span>
              </div>
            </a>

            <a href="mailto:admin@dpricebuilders.com" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M4 4H20C21.1 4 22 4.9 22 6V18C22 19.1 21.1 20 20 20H4C2.9 20 2 19.1 2 18V6C2 4.9 2.9 4 4 4Z" stroke="currentColor" stroke-width="2"/>
                  <path d="M22 6L12 13L2 6" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <div class="method-text">
                <strong>Email Us</strong>
                <span>admin@dpricebuilders.com</span>
              </div>
            </a>

            <a href="https://wa.me/447738664699" target="_blank" rel="noopener" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z" fill="currentColor"/>
                </svg>
              </div>
              <div class="method-text">
                <strong>WhatsApp</strong>
                <span>Message us directly</span>
              </div>
            </a>
          </div>

          <div class="social-links">
            <a href="https://www.facebook.com/DPBCLtd/" target="_blank" rel="noopener" aria-label="Visit our Facebook page">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
              </svg>
            </a>
            <a href="https://www.instagram.com/dpricebuildersgloucester/" target="_blank" rel="noopener" aria-label="Visit our Instagram page">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
            </a>
            <a href="https://www.linkedin.com/in/jason-price-080b9735/" target="_blank" rel="noopener" aria-label="Visit Jason Price's LinkedIn profile">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
          </div>
        </div>

        <div class="contact-visual">
          <div class="visual-text">
            <div class="visual-line">Quality.</div>
            <div class="visual-line">Integrity.</div>
            <div class="visual-line">Craftsmanship.</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-container">
        <div class="footer-brand">
          <img :src="logo" alt="DPrice Builders" />
          <p>David Price Building Contractors Ltd</p>
          <p class="footer-tagline">Building excellence since 1966</p>
        </div>

        <div class="footer-links">
          <div class="footer-column">
            <h4>Services</h4>
            <a href="#services">Extensions</a>
            <a href="#services">Loft Conversions</a>
            <a href="#services">Renovations</a>
            <a href="#services">View All Services</a>
          </div>

          <div class="footer-column">
            <h4>Company</h4>
            <a href="#heritage">Our Heritage</a>
            <a href="#portfolio">Portfolio</a>
            <a href="#contact">Contact</a>
          </div>

          <div class="footer-column">
            <h4>Contact</h4>
            <a href="tel:07738664699">07738 664699</a>
            <a href="mailto:admin@dpricebuilders.com">admin@dpricebuilders.com</a>
            <p class="footer-location">Gloucestershire, UK</p>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; 2024 David Price Building Contractors Ltd. All rights reserved.</p>
        <div class="footer-legal">
          <a href="/privacy">Privacy Policy</a>
          <span>·</span>
          <a href="/terms">Terms</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<style src="./styles.css"></style>
