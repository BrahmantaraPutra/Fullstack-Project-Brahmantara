<script setup lang="ts">
import ContactCard from "./components/ContactCard.vue";
import FeatureCard from "./components/FeatureCard.vue";
import ProjectCard from "./components/ProjectCard.vue";
import TechCard from "./components/TechCard.vue";
import TimelineItem from "./components/TimelineItem.vue";
import pfp from "./Assets/pfp.jpg";

const navigation = ["About", "Tech", "Focus", "Projects", "Certificates", "Edukasi", "Contact"];

const stats = [
  { value: "10+", label: "Project selesai" },
  { value: "2+", label: "Tahun belajar" },
  { value: "10+", label: "Teknlogi dipelajari" },
];

const techList = [
  {
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kotlin/kotlin-original.svg",
    label: "Kotlin Native",
    detail: "Mobile app Android native dengan kecepatan dan stabilitas terbaik.",
  },
  {
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg",
    label: "Flutter",
    detail: "UI mobile lintas platform dengan animasi halus dan pengalaman konsisten.",
  },
  {
    icon: "https://upload.wikimedia.org/wikipedia/commons/b/bc/Avalonia_logo.svg?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original",
    label: "Avalonia",
    detail: "Aplikasi desktop Windows dan cross-platform dengan antarmuka modern.",
  },
  {
    icon: "https://upload.wikimedia.org/wikipedia/commons/d/d5/Rust_programming_language_black_logo.svg?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original",
    label: "Tauri",
    detail: "Desktop app ringan dengan keamanan dan integrasi web native.",
  },
  {
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg",
    label: "Vue.js",
    detail: "Framework web reaktif untuk antarmuka pengguna yang cepat dan modular.",
  },
  {
    icon: "https://upload.wikimedia.org/wikipedia/commons/9/9a/Laravel.svg?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original",
    label: "Laravel",
    detail: "Backend PHP terstruktur untuk API, CMS, dan aplikasi web fullstack.",
  },
  {
    icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg",
    label: "PostgreSQL",
    detail: "Database relasional untuk data berskala besar dan integritas kuat.",
  },
  {
    icon: "https://upload.wikimedia.org/wikipedia/commons/4/41/Microsoft_SQL_Server_2025_icon.svg?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original",
    label: "SQL Server",
    detail: "Database enterprise dengan kemampuan analitik dan transaksi andal.",
  },
];

const focusList = [
  {
    title: "Mobile App",
    description:
      "Membangun aplikasi mobile dengan Native Kotlin dan Flutter untuk pengalaman pengguna yang lancar.",
  },
  {
    title: "Desktop App",
    description:
      "Mengembangkan aplikasi desktop menggunakan WPF, Avalonia, dan Tauri untuk performa maksimal.",
  },
  {
    title: "Website",
    description: "Menciptakan website profesional dengan Vue di frontend dan Laravel pada backend.",
  },
];

const projectList = [
  {
    title: "Smith Origin",
    subtitle: "Aplikasi desktop untuk manajemen data",
    description:
      "Aplikasi desktop cross-platform yang berfokus pada efisiensi performa, dikembangkan dengan Tauri menuju arsitektur modern",
    tags: ["Dashboard", "Admin", "Tauri", "Rust", "Vue.js", "PostgreSQL"],
  },
  {
    title: "Ezemkofie ( Mobile )",
    subtitle: "Aplikasi mobile untuk proses jual beli cafe",
    description:
      "Aplikasi Android native untuk manajemen inventaris dan transaksi sebuah kafe, menggunakan arsitektur MVVM dan integrasi REST API.",
    tags: ["Kotlin", "UX", "Jatpack Compose", "Retrofit", "MVVM"],
  },
];

const certificates = [
  {
    title: "LKS Provinsi DIY 2026",
    description:
      "Meraih Juara 2 tingkat Provinsi dalam Lomba Kompetensi Siswa cabang IT Software Solution for Business.",
  },
  {
    title: "Tecnoversary - EcoDigital for Environment",
    description:
      "Menjadi finalis dalam lomba membangun dan mendesain sebuah webite bertema edukasi lingkungan.",
  },
  {
    title: "MTCNA",
    description:
      "Sertifikasi resmi dari MikroTik untuk mengkonfigurasi, mengelola, dan menggunakan MikroTik RouterOS",
  },
];

const timeline = [
  {
    year: "2023 - 2027",
    title: "SMK Negeri 2 Yogyakarta",
    subtitle: "Sistem Informasi Jaringan dan Aplikasi",
    description:
      "Menjalani pendidikan teknologi dengan fokus pemrograman, basis data, dan pengembangan aplikasi.",
    image:
      "https://media.licdn.com/dms/image/v2/C561BAQFqoSaL0Q8kQQ/company-background_10000/company-background_10000/0/1608363398327/smk_negeri_2_yogyakarta_cover?e=2147483647&v=beta&t=4snbs2TkpZLEicWdNqeER8wMqlBwTWLLzvcMSpyVd0I",
  },
];

const contacts = [
  {
    label: "Email",
    value: "brahmantaraputraw@gmail.com",
    href: "mailto:brahmantaraputraw@gmail.com",
  },
  {
    label: "GitHub",
    value: "github.com/BrahmantaraPutra",
    href: "https://github.com/BrahmantaraPutra",
  },
  {
    label: "LinkedIn",
    value: "linkedin.com/in/brahmantara-putra-wirabhakti",
    href: "https://id.linkedin.com/in/brahmantara-putra-wirabhakti-55128736b",
  },
];
</script>

<template>
  <div class="page-shell">
    <header class="site-header">
      <div class="brand">Brahmantara Putra</div>
      <nav class="site-nav" aria-label="Main navigation">
        <a v-for="item in navigation" :key="item" :href="`#${item.toLowerCase()}`">{{ item }}</a>
      </nav>
      <a href="#" class="header-cta" @click.prevent>Portfolio</a>
    </header>

    <main>
      <section class="hero-section" id="about">
        <div class="hero-copy">
          <span class="hero-badge">Siswa | SMK Negeri 2 Yogyakarta</span>
          <h1>Halo, saya <br><span>Brahmantara Putra.</span></h1>
          <p>
            Seorang siswa SMK yang berfokus pada pengembangan aplikasi mobile & desktop. Saat ini
            sedang mencari kesempatan magang untuk mengasah keahlian di lingkungan kerja nyata.
            Selamat datang di ruang dokumentasi karya dan perjalanan belajar saya.
          </p>
          <div class="hero-actions">
            <a href="#tech" class="button button--primary">Lihat Tech Stack</a>
            <a href="#projects" class="button button--secondary">Jelajah Project</a>
          </div>
          <div class="hero-meta">
            <div>
              <strong>Yogyakarta, ID</strong>
              <span>Available for Project</span>
            </div>
            <div>
              <strong>Mobile • Desktop • Web</strong>
              <span>Native, Cross-platform, Fullstack</span>
            </div>
          </div>
        </div>
        <div class="hero-visual">
          <div class="hero-visual__shape"></div>
          <div class="hero-visual__profile">
            <div class="hero-visual__photo">
              <img :src="pfp" alt="Brahmantara Putra" class="hero-photo-img" />
            </div>
          </div>
        </div>
      </section>

      <section class="about-section">
        <div class="section-heading">
          <p class="section-label">About</p>
          <h2>Tentang Saya</h2>
        </div>
        <div class="about-text">
          <p>
            Saya seorang siswa SMK jurusan IT yang antusias pada dunia pengembangan aplikasi mobile,
            desktop, dan web. Saya banyak belajar secara mandiri sambil mengikuti berbagai
            kompetensi dan kompetisi di sekolah.
          </p>
          <p>
            Saat ini saya sedang mencari kesempatan magang (PKL) untuk menerapkan keahlian saya di
            lingkungan profesional. Stack favorit: Kotlin (Android), Flutter, Avalonia (.NET), serta
            Tauri (Rust) untuk desktop ringan.
          </p>
        </div>
        <div class="about-stats-row">
          <article v-for="stat in stats" :key="stat.label" class="stat-card">
            <strong>{{ stat.value }}</strong>
            <span>{{ stat.label }}</span>
          </article>
        </div>
      </section>

      <section class="tech-section" id="tech">
        <div class="section-heading">
          <p class="section-label">Tech Stack</p>
          <h2>Teknologi yang Saya Gunakan</h2>
        </div>
        <div class="tech-grid">
          <TechCard
            v-for="tech in techList"
            :key="tech.label"
            :icon="tech.icon"
            :label="tech.label"
            :detail="tech.detail"
          />
        </div>
      </section>

      <section class="skills-section" id="focus">
        <div class="section-heading">
          <p class="section-label">Focus</p>
          <h2>Keahlian Utama</h2>
        </div>
        <div class="feature-grid">
          <FeatureCard
            v-for="skill in focusList"
            :key="skill.title"
            :title="skill.title"
            :description="skill.description"
          />
        </div>
      </section>

      <section class="projects-section" id="projects">
        <div class="section-heading">
          <p class="section-label">Projects</p>
          <h2>Pengalaman Projek</h2>
        </div>
        <div class="project-grid">
          <ProjectCard
            v-for="project in projectList"
            :key="project.title"
            :title="project.title"
            :subtitle="project.subtitle"
            :description="project.description"
            :tags="project.tags"
          />
        </div>
      </section>

      <section class="certificates-section" id="certificates">
        <div class="section-heading">
          <p class="section-label">Certificates</p>
          <h2>Sertifikat & Pencapaian</h2>
        </div>
        <div class="certificate-grid">
          <FeatureCard
            v-for="item in certificates"
            :key="item.title"
            :title="item.title"
            :description="item.description"
          />
        </div>
      </section>

      <section class="timeline-section" id="edukasi">
        <div class="section-heading">
          <p class="section-label">Edukasi</p>
          <h2>Pendidikan</h2>
        </div>
        <div class="timeline-grid">
          <TimelineItem
            v-for="item in timeline"
            :key="item.title"
            :year="item.year"
            :title="item.title"
            :subtitle="item.subtitle"
            :description="item.description"
            :image="item.image"
          />
        </div>
      </section>
    </main>

    <footer class="page-footer" id="contact">
      <div class="footer-heading">
        <p class="section-label">Get In Touch</p>
        <h2>Mari Terhubung</h2>
      </div>
      <div class="contact-grid">
        <ContactCard
          v-for="contact in contacts"
          :key="contact.label"
          :label="contact.label"
          :value="contact.value"
          :href="contact.href"
        />
      </div>
      <p class="footer-copyright">Brahmantara. © 2026 Brahmantara Putra. All rights reserved.</p>
    </footer>
  </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}
:root {
  color-scheme: dark;
  font-family:
    Inter,
    ui-sans-serif,
    system-ui,
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;
  color: #efede9;
  background: #131a23;
}
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  background: #131a23;
  color: #efede9;
}
.page-shell {
  max-width: 1296px;
  margin: 0 auto;
  padding: 24px 24px 40px;
}
.site-header {
  position: sticky;
  top: 0;
  z-index: 40;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1rem 0;
  background: rgba(19, 26, 35, 0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(203, 142, 102, 0.15);
}
.brand {
  font-weight: 800;
  font-size: 1.2rem;
  color: #efede9;
}
.site-nav {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  align-items: center;
}
.site-nav a {
  color: #efede9;
  text-decoration: none;
  font-size: 0.95rem;
  padding: 0.55rem 0.75rem;
  border-radius: 9999px;
  transition:
    background 0.25s ease,
    color 0.25s ease;
}
.site-nav a:hover,
.site-nav a:focus-visible {
  color: #131a23;
  background: #cb8e66;
}
.header-cta {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 9999px;
  padding: 0.95rem 1.35rem;
  background: #cb8e66;
  color: #131a23;
  text-decoration: none;
  font-weight: 700;
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}
.header-cta:hover {
  transform: translateY(-1px);
  box-shadow: 0 15px 30px rgba(44, 49, 58, 0.12);
}
.hero-section {
  display: grid;
  grid-template-columns: minmax(0, 1.1fr) minmax(260px, 0.7fr);
  gap: 2.5rem;
  align-items: center;
  padding: 2.5rem 0 3rem;
}
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.55rem;
  padding: 0.7rem 1rem;
  border-radius: 9999px;
  background: rgba(203, 142, 102, 0.18);
  color: #efede9;
  font-size: 0.85rem;
  font-weight: 700;
  margin-bottom: 1.4rem;
}
.hero-section h1 {
  font-size: clamp(2.5rem, 4vw, 4rem);
  line-height: 1.02;
  margin: 0;
  color: #efede9;
}
.hero-section h1 span {
  color: #cb8e66;
}
.hero-section p {
  max-width: 620px;
  color: #d8d4cf;
  margin: 1.4rem 0 2rem;
  line-height: 1.85;
}
.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-bottom: 2rem;
}
.button {
  border-radius: 9999px;
  padding: 1rem 1.6rem;
  font-weight: 700;
  text-decoration: none;
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}
.button:hover {
  transform: translateY(-2px);
}
.button--primary {
  background: #2c313a;
  color: #efede9;
}
.button--secondary {
  background: rgba(255, 255, 255, 0.08);
  color: #efede9;
}
.hero-meta {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(2, minmax(0, 1fr));
}
.hero-meta div {
  border-radius: 20px;
  background: rgba(19, 26, 35, 0.92);
  padding: 1.1rem 1.25rem;
  border: 1px solid rgba(203, 142, 102, 0.16);
}
.hero-meta strong {
  display: block;
  font-size: 1rem;
  margin-bottom: 0.4rem;
  color: #efede9;
}
.hero-meta span {
  color: #a5a097;
  font-size: 0.92rem;
}
.hero-visual {
  position: relative;
  min-height: 340px;
  display: grid;
  place-items: center;
}
.hero-visual__shape {
  position: absolute;
  inset: 0;
  border-radius: 40px;
  background:
    radial-gradient(circle at top left, rgba(203, 142, 102, 0.18), transparent 42%),
    radial-gradient(circle at bottom right, rgba(98, 79, 69, 0.12), transparent 35%);
}
.hero-visual__profile {
  position: relative;
  width: 100%;
  height: 100%;
  display: grid;
  place-items: center;
}
.hero-visual__photo {
  width: min(220px, 100%);
  aspect-ratio: 1 / 1;
  border-radius: 50%;
  background: linear-gradient(180deg, #efede9 0%, #cb8e66 100%);
  box-shadow: 0 30px 60px rgba(44, 49, 58, 0.16);
  position: relative;
  overflow: hidden;
}
.hero-visual__photo::before,
.hero-visual__photo::after {
  /* Remove dark overlay effects so the profile image displays naturally */
  display: none;
}

.hero-photo-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  position: relative;
  z-index: 1;
}
.hero-visual__photo::before,
.hero-visual__photo::after {
  display: none;
}

.section-heading {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
  margin-bottom: 1.8rem;
}
.section-heading h2 {
  color: #efede9;
}
.section-label {
  text-transform: uppercase;
  letter-spacing: 0.18em;
  font-size: 0.75rem;
  font-weight: 700;
  color: #cb8e66;
}
.about-section,
.tech-section,
.skills-section,
.projects-section,
.certificates-section,
.timeline-section {
  padding: 3rem 0;
}
.about-text p {
  color: #d8d4cf;
  line-height: 1.9;
  margin: 0 0 1.25rem;
}
.about-stats-row {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 1.75rem;
}
.stat-card {
  flex: 1 1 180px;
  min-width: 180px;
  border-radius: 24px;
  padding: 1.4rem 1.5rem;
  background: rgba(19, 26, 35, 0.92);
  border: 1px solid rgba(203, 142, 102, 0.16);
  box-shadow: 0 18px 35px rgba(44, 49, 58, 0.16);
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.stat-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 22px 40px rgba(44, 49, 58, 0.2);
}
.stat-card strong {
  display: block;
  font-size: 2rem;
  margin-bottom: 0.35rem;
  color: #efede9;
}
.stat-card span {
  color: #a5a097;
}
.tech-grid,
.feature-grid,
.project-grid,
.certificate-grid,
.timeline-grid,
.contact-grid {
  display: grid;
  gap: 1.5rem;
}
.tech-grid {
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
.feature-grid,
.project-grid,
.certificate-grid {
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}
.timeline-grid {
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
}
.contact-grid {
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
}
.page-footer {
  padding: 3rem 0 1rem;
}
.footer-heading {
  margin-bottom: 2rem;
}
.footer-heading h2 {
  margin: 0;
}
.footer-copyright {
  color: #94a3b8;
  text-align: center;
  margin-top: 2.5rem;
}
@media (max-width: 980px) {
  .hero-section,
  .about-grid {
    grid-template-columns: 1fr;
  }
  .hero-visual {
    min-height: 320px;
  }
}
@media (max-width: 720px) {
  .page-shell {
    padding: 20px 18px 30px;
  }
  .site-header {
    flex-direction: column;
    align-items: flex-start;
  }
  .site-nav {
    gap: 0.75rem;
  }
  .hero-actions {
    flex-direction: column;
  }
  .hero-meta {
    grid-template-columns: 1fr;
  }
}
</style>
