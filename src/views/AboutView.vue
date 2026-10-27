<script setup lang="ts"></script>

<template>
  <div class="about-page">
    <!-- Intro / Hero Section -->
    <section class="profile-hero">
      <div class="container">
        <div class="profile-grid">
          <div class="profile-image">
            <img src="@/assets/images/photo.png" alt="Storm Laan" />
          </div>
          <div class="profile-info">
            <h1>Storm Laan</h1>
            <p class="role">Software & Hardware Developer | Oprichter Olytech.</p>
            <p>
              Ik ben gepassioneerd door het bouwen van complete oplossingen — van de fysieke
              hardware en PCB-ontwerpen tot de backend-systemen en webinterfaces. Met ervaring in
              onder andere Vue.js, Rust, microcontrollers en 3D-ontwerp vind ik het leuk om ideeën
              om te zetten in werkende projecten. Daarnaast beheer ik mijn eigen servers om
              applicaties en websites zelf te hosten.
            </p>

            <div class="contact-chips">
              <a href="mailto:vlekkie.storm@gmail.com" class="chip">✉️ stormlaan@icloud.com</a>
              <a href="tel:0651479557" class="chip">📞 06 51479557</a>
              <span class="chip">📍 Nieuwe Niedorp</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Opleiding & Werkervaring -->
    <section class="experience-section">
      <div class="container grid-2col">
        <!-- Werkervaring -->
        <div class="cv-block">
          <h2>Werk & Stage Ervaring</h2>
          <div class="timeline">
            <div class="timeline-item">
              <span class="date">Opdracht</span>
              <h3>Project Ontwikkelaar — FBE Noord-Holland</h3>
              <p class="description">
                Ontwikkeling van de publieke website
                <a href="https://telgebieden.nl/" target="_blank" rel="noopener">telgebieden.nl</a>
                en een intern dashboard voor valwild-registratie.
              </p>
            </div>

            <div class="timeline-item">
              <span class="date">Opdracht</span>
              <h3>AI Developer — Digital Card Solutions (DCS)</h3>
              <p class="description">
                Ontwikkeling van een AI-model voor de automatische classificatie van dieren.
              </p>
            </div>

            <div class="timeline-item">
              <span class="date">2024</span>
              <h3>Software Stagiair — KIKSAUS</h3>
              <p class="description">Bewerken en maken van websites in php, vue3 en SCSS.</p>
            </div>

            <div class="timeline-item">
              <span class="date">2022 — 2024</span>
              <h3>Assemblage & Hardware Technicus — Miniot Schagen</h3>
              <p class="description">
                Klaarmaken van motoren en assembleren van moederborden voor hoogwaardige
                platenspelers.
              </p>
            </div>

            <div class="timeline-item">
              <span class="date">2023</span>
              <h3>Software Stagiair — VWE</h3>
              <p class="description">Bewerken van website-templates in HTML en CSS.</p>
            </div>

            <div class="timeline-item">
              <span class="date">2021 — 2022</span>
              <h3>Stagiair — CPJ Techniek</h3>
              <p class="description">Verspanen op CNC-machines, ontbramen, zagen en assemblage.</p>
            </div>
          </div>
        </div>

        <!-- Opleidingen -->
        <div class="cv-block">
          <h2>Opleidingen</h2>
          <div class="timeline">
            <div class="timeline-item">
              <span class="date">2025 — 2026</span>
              <h3>HBO Elektrotechniek (Voltijd)</h3>
              <span class="location">Hogeschool Inholland Alkmaar</span>
              <p class="description">
                Diepgaande kennis opgebouwd over PCB-ontwerp, schema-tekenen en elektronische
                componenten.
              </p>
            </div>

            <div class="timeline-item">
              <span class="date">2022 — 2025</span>
              <h3>MBO 4 Software Developer</h3>
              <span class="location">VONK Schagen</span>
              <p class="description">
                Webapplicaties gebouwd met PHP, JavaScript, HTML, CSS en MySQL. Gewerkt met Agile
                methodieken (Trello, Figma, Git).
              </p>
            </div>

            <div class="timeline-item">
              <span class="date">2018 — 2022</span>
              <h3>VMBO Kader (Cum Laude)</h3>
              <span class="location">Regius College Schagen</span>
              <p class="description">
                Gespecialiseerd in Produceren, Installeren & Energie. Ervaring opgedaan met
                SolidWorks (3D printen), CNC-draaibanken en robot-programmering.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Vaardigheden & Passies -->
    <section class="skills-hobbies-section">
      <div class="container">
        <h2>Expertise & Hobby's</h2>
        <div class="cards-grid">
          <div class="card">
            <h3>Schematic & PCB Design</h3>
            <p>
              Zelfstandig uittekenen van scheSchema's, PCB layout ontwerp en bestellen van custom
              printplaten.
            </p>
          </div>

          <div class="card">
            <h3>3D CAD & Prototyping</h3>
            <p>
              Modelleren in Fusion 360 en SolidWorks. Ontwerpen van functionele onderdelen en
              behuizingen (o.a. custom game-controllers).
            </p>
          </div>

          <div class="card">
            <h3>Software & Web Development</h3>
            <p>
              Ervaring met Vue 3, TypeScript, SCSS, Rust, PHP, HTML/CSS en MySQL databasebeheer.
            </p>
          </div>

          <div class="card">
            <h3>Systems & Servers</h3>
            <p>
              Eigen servers beheren voor hosting en applicaties met behulp van Ubuntu Server en
              Proxmox VE.
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped lang="scss">
.about-page {
  color: #eeead7;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Profile Hero */
.profile-hero {
  background: #757d6f;
  padding: 50px 0;

  .profile-grid {
    display: flex;
    flex-direction: column;
    gap: 30px;
    align-items: center;

    @media (min-width: 768px) {
      flex-direction: row;
      gap: 50px;
    }
  }

  .profile-image img {
    width: 300px;
    object-fit: cover;
    border-radius: 12px;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  }

  .profile-info {
    h1 {
      margin: 0;
      font-size: 2.2rem;
      color: #fff;
    }

    .role {
      font-size: 1.1rem;
      font-weight: 600;
      color: #eeead7;
      margin: 5px 0 15px;
    }

    .bio {
      line-height: 1.6;
      margin-bottom: 20px;
      color: #eeead7;
    }

    .contact-chips {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;

      .chip {
        background: rgba(0, 0, 0, 0.2);
        color: #fff;
        padding: 6px 14px;
        border-radius: 20px;
        font-size: 0.85rem;
        text-decoration: none;
        transition: background 0.2s;

        &:hover {
          background: rgba(0, 0, 0, 0.35);
        }
      }
    }
  }
}

/* Experience & Education Section */
.experience-section {
  background: #1c201a;
  padding: 60px 0;

  .grid-2col {
    display: grid;
    grid-template-columns: 1fr;
    gap: 40px;

    @media (min-width: 768px) {
      grid-template-columns: 1fr 1fr;
    }
  }

  .cv-block h2 {
    color: #fff;
    font-size: 1.5rem;
    margin-bottom: 25px;
    border-bottom: 2px solid #757d6f;
    padding-bottom: 8px;
  }
}

/* Timeline Components */
.timeline {
  display: flex;
  flex-direction: column;
  gap: 24px;

  .timeline-item {
    position: relative;
    padding-left: 20px;
    border-left: 2px solid #757d6f;

    .date {
      font-size: 0.8rem;
      font-weight: 700;
      color: #b5baae;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    h3 {
      margin: 4px 0 2px;
      font-size: 1.1rem;
      color: #fff;
    }

    .location {
      display: block;
      font-size: 0.85rem;
      color: #9aa091;
      margin-bottom: 6px;
    }

    .description {
      font-size: 0.9rem;
      line-height: 1.5;
      color: #b5baae;
      margin: 0;

      a {
        color: #08c256;
        text-decoration: none;
        &:hover {
          text-decoration: underline;
        }
      }
    }
  }
}

.skills-hobbies-section {
  background: #5e6659;
  padding: 60px 0;

  h2 {
    color: #fff;
    font-size: 1.5rem;
    margin-bottom: 30px;
    text-align: center;
  }

  .cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;

    .card {
      background: rgba(0, 0, 0, 0.2);
      padding: 20px;
      border-radius: 10px;

      h3 {
        margin-top: 0;
        margin-bottom: 10px;
        font-size: 1.1rem;
        color: #fff;
      }

      p {
        margin: 0;
        font-size: 0.9rem;
        line-height: 1.5;
        color: #eeead7;
      }
    }
  }
}
</style>
