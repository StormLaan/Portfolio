<script setup lang="ts"></script>

<template>
  <!-- About -->
  <section class="about-section">
    <div class="container">
      <h1>About Me</h1>
      <div class="content">
        <img src="@/assets/images/photo.png" alt="storm laan" />
        <div class="bio">
          <h1>Hi, I'm <strong>Storm Laan</strong></h1>
          <p class="role">Software & Hardware Developer | Oprichter Olytech.</p>
          <p>
            Ik ben gepassioneerd door het bouwen van complete oplossingen — van de fysieke hardware
            en PCB-ontwerpen tot de backend-systemen en webinterfaces. Met ervaring in onder andere
            Vue.js, Rust, microcontrollers en 3D-ontwerp vind ik het leuk om ideeën om te zetten in
            werkende projecten. Daarnaast beheer ik mijn eigen servers om applicaties en websites
            zelf te hosten.
          </p>
        </div>
      </div>
    </div>
  </section>
  <section style="background: #eeead7; color: #000">
    <div class="container">
      <h1>Projects</h1>
      <div class="projects">
        <div class="project">
          <img src="@/assets/images/controller.png" alt="Handheld" />
          <div class="project-content"></div>
          <h1>Handheld</h1>
          <div>
            Een soort Nintendo switch met de opties om het te gebruiken met een draad aangesloten
            computer of een direct aangesloten. Met dat kan je je eigen computer vervangen met een
            nieuwe of gewoon koppelen aan je bestaande laptop of computer. .
          </div>
          <!--          <button>MORE ></button>-->
        </div>

        <div class="project">
          <!--          <img />-->
          <div class="project-content"></div>
          <h1>Olybase</h1>
          <div>
            Olybase is een pakket gebouwd op rust met axum met meerdere optionele pakketten om een
            api of front end net wat sneller te kunnen maken. Daarin zitten optionele pakketten:
            <ul>
              <li>Axum met standaard responses, cors, tls, tracing en websocket support</li>
              <li>Jwt en refresh token generatie en validatie</li>
              <li>Password hasher</li>
              <li>Storage via s3</li>
            </ul>
          </div>
          <a target="_blank" href="https://github.com/olytech-official/olybase">MORE ></a>
        </div>

        <div class="project">
          <img src="@/assets/images/HomeServer.jpg" />
          <div class="project-content"></div>
          <h1>Home server</h1>
          <div>
            Ik heb ervaring met het opzetten en beheren van mijn eigen home server met behulp van
            Ubuntu Server, Proxmox en HexOS. Momenteel host ik deze portfolio en verschillende
            andere zelfgemaakte websites rechtstreeks op mijn eigen server.
          </div>
          <!--          <button>MORE ></button>-->
        </div>
      </div>
    </div>
  </section>

  <section class="skills-section">
    <div class="container">
      <h1>Vaardigheden & Tools</h1>
      <p class="subtitle">
        Een overzicht van technologieën en middelen waar ik mee werk binnen verschillende domeinen.
      </p>
      <div class="skills-grid">
        <div class="skill">
          <div class="skill-header">
            <h2>Software</h2>
          </div>
          <ul class="skill-list">
            <li>Vue.js</li>
            <li>TypeScript</li>
            <li>PHP</li>
            <li>Rust</li>
            <li>Git</li>
          </ul>
        </div>

        <div class="skill">
          <div class="skill-header">
            <h2>Hardware & Elektronica</h2>
          </div>
          <ul class="skill-list">
            <li>EasyEDA</li>
            <li>PCB Layout & Ontwerp</li>
            <li>Microcontrollers (RP2040)</li>
          </ul>
        </div>

        <div class="skill">
          <div class="skill-header">
            <h2>CAD</h2>
          </div>
          <ul class="skill-list">
            <li>Fusion 360</li>
            <li>SolidWorks</li>
            <li>3D-printen</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
section {
  background: #757d6f;
  padding: 25px;
}

.container {
  max-width: 1000px;
  margin: 0 auto;

  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;

    @media (min-width: 768px) {
      flex-direction: row;
      gap: 100px;
    }

    p {
      @media (min-width: 768px) {
        width: 100%;
      }
    }

    img {
      width: 300px;
      object-fit: cover;
      border-radius: 12px;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);

      @media (min-width: 768px) {
        max-width: 250px;
      }
    }
  }

  a {
    color: #08c256;
  }
}

.projects {
  display: flex;
  flex-direction: row;
  gap: 15px;
  justify-content: space-between;

  @media (max-width: 768px) {
    flex-direction: column;
  }
}

.project {
  width: 100%;
  background: var(--box);
  border-radius: 10px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  color: #fff;

  h1,
  p {
    margin: 0;
  }

  ul {
    list-style: inside;
    padding-left: 10px;

    li {
      margin-bottom: 5px;
      margin-top: 5px;
    }
  }

  a,
  button {
    width: min-content;
    text-wrap: nowrap;
    text-decoration: none;
    padding: 5px;
    border-radius: 8px;
    background: #757d6f;
    border: none;
    margin-top: 5px;
    color: #fff;

    &:hover {
      filter: brightness(1.2);
    }
  }

  img {
    width: 100%;
    height: 200px;
    background: #9e9e9e;
    border-radius: 10px;
    margin-bottom: 5px;
    object-fit: cover;
  }
}

.about-section {
  .bio {
    display: flex;
    flex-direction: column;

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

    p {
      font-size: 1rem;
      line-height: 1.6;
      color: #eeead7;
      margin: 0;

      strong {
        color: #fff;
      }
    }
  }
}

.skills-section {
  background: #5e6659;
  color: #fff;

  .subtitle {
    margin-top: -10px;
    margin-bottom: 30px;
    opacity: 0.85;
    font-size: 0.95rem;
  }
}

.skills-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;

  @media (min-width: 768px) {
    grid-template-columns: repeat(3, 1fr);
  }

  .skill {
    background: rgba(0, 0, 0, 0.15);
    border-radius: 10px;
    padding: 15px 30px;
    margin-top: 10px;
    transition:
      transform 0.2s ease,
      box-shadow 0.2s ease;

    &:hover {
      transform: translateY(-4px);
      background: rgba(0, 0, 0, 0.22);
    }

    .skill-header {
      line-height: 1;
      margin-bottom: 10px;
    }
  }
}

.skill-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;

  li {
    background: #eeead7;
    color: #2b3027;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 6px 14px;
    border-radius: 20px;
    white-space: nowrap;
  }
}
</style>
