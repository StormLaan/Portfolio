<script setup lang="ts">
import Nav from '@/components/nav.vue'
</script>

<template>
  <div class="dark root" id="top">
    <Nav>
      <div class="nav-buttons-section">
        <RouterLink to="/" active-class="selected">Home</RouterLink>
      </div>
      <div class="nav-buttons-section">
        <!--        <RouterLink to="/projects" active-class="selected">Projects</RouterLink>-->
        <RouterLink to="/about" active-class="selected">About</RouterLink>
      </div>
    </Nav>

    <header :class="{ big: $route.path === '/' }">
      <div class="image-wrapper">
        <img src="@/assets/images/controller.png" alt="logo" />
        <div class="image-overlay"></div>
      </div>

      <div class="sidebar">
        <div class="sidebar-content">
          <h1>Storm's portfolio website</h1>
          <h2>Software & Hardware Developer | Oprichter Olytech.</h2>
        </div>
      </div>
    </header>

    <main id="main-content">
      <RouterView />
    </main>

    <footer>
      <div class="footer-container">
        <!-- Brand & Mission Column -->
        <div class="footer-col brand-col">
          <div class="brand-logo">
            <span class="company-name">Olytech</span>
            <span class="tagline">By Storm Laan</span>
          </div>
          <p class="brand-desc">
            Designing repairable, open-source hardware and durable software. Built to last, easy to
            modify.
          </p>
          <p class="copyright">© {{ new Date().getFullYear() }} Olytech / Storm Laan.</p>
        </div>

        <!-- Quick Links Column -->
        <div class="footer-col links-col">
          <h3>Navigation</h3>
          <ul>
            <li><RouterLink to="/">Home</RouterLink></li>
            <li><RouterLink to="/projects">Projects</RouterLink></li>
            <li><RouterLink to="/about">About</RouterLink></li>
          </ul>
        </div>

        <!-- Code & Profielen -->
        <div class="footer-col links-col">
          <h3>Developer Links</h3>
          <ul>
            <li>
              <a href="https://github.com/StormLaan" target="_blank" rel="noopener"
                >Personal GitHub</a
              >
            </li>
            <li>
              <a href="https://github.com/olytech-official" target="_blank" rel="noopener"
                >Olytech GitHub</a
              >
            </li>
            <li><a href="#top" class="top-link">Naar boven ↑</a></li>
          </ul>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped lang="scss">
header {
  width: 100%;
  display: flex;
  background: var(--box, #1c201a);
  color: #eeead7;
  overflow: hidden;
  height: 40vh;

  &.big {
    min-height: 100dvh;
  }

  @media (max-width: 768px) {
    flex-direction: column;
    min-height: auto;
    height: auto;
  }

  .image-wrapper {
    position: relative;
    width: 85%;
    min-height: 100%;

    @media (max-width: 768px) {
      width: 100%;
      height: 320px;
    }

    img {
      height: 100%;
      width: 100%;
      object-fit: cover;
      display: block;
    }

    .image-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(90deg, rgba(0, 0, 0, 0.2) 0%, rgba(28, 32, 26, 0.8) 100%);

      @media (max-width: 768px) {
        background: linear-gradient(180deg, rgba(0, 0, 0, 0.1) 0%, rgba(28, 32, 26, 1) 100%);
      }
    }
  }

  .sidebar {
    padding: 60px 40px;
    display: flex;
    justify-content: center;
    align-items: center;

    .sidebar-content {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 16px;

      @media (max-width: 768px) {
        align-items: center;
        text-align: center;
      }

      h1 {
        font-weight: 800;
        line-height: 1.15;
        letter-spacing: -0.5px;
        margin: 0;
        color: #ffffff;
      }

      h2 {
        font-size: 16px;
        font-weight: 400;
        line-height: 1.5;
        color: #b5baae;
        margin: 0;
      }
    }
  }
}

.nav-buttons-section {
  display: flex;
  gap: 10px;

  @media (max-width: 768px) {
    flex-direction: column;
    width: 100%;

    a,
    button {
      text-align: center;
    }
  }
}

a,
button {
  text-decoration: none;
  padding: 10px;
  color: black;
  font-weight: bold;
  font-size: 16px;
  color: #fff;

  &:hover,
  &:active,
  &.selected {
    text-decoration: underline;
  }
}

footer {
  background: #232720;
  color: #eeead7;
  padding: 60px 25px 40px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);

  .footer-container {
    max-width: 1000px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 40px;
    align-items: start;

    @media (max-width: 768px) {
      grid-template-columns: 1fr 1fr;
    }

    @media (max-width: 500px) {
      grid-template-columns: 1fr;
      gap: 30px;
      text-align: center;
    }
  }

  .footer-col {
    h3 {
      font-size: 1.1rem;
      margin-top: 0;
      margin-bottom: 15px;
      color: #fff;
    }

    ul {
      list-style: none;
      padding: 0;
      margin: 0;

      li {
        margin-bottom: 10px;

        a {
          color: #b5baae;
          text-decoration: none;
          font-size: 0.95rem;
          transition: color 0.2s ease;

          &:hover {
            color: #eeead7;
            text-decoration: underline;
          }
        }
      }
    }
  }

  .brand-col {
    .brand-logo {
      display: flex;
      align-items: baseline;
      gap: 10px;
      margin-bottom: 12px;

      @media (max-width: 500px) {
        justify-content: center;
      }

      .company-name {
        font-size: 1.6rem;
        font-weight: 800;
        letter-spacing: 0.5px;
        color: #fff;
      }

      .tagline {
        font-size: 0.85rem;
        color: #9aa091;
      }
    }

    .brand-desc {
      font-size: 0.9rem;
      line-height: 1.5;
      color: #b5baae;
      margin-bottom: 20px;
      max-width: 380px;

      @media (max-width: 500px) {
        margin-left: auto;
        margin-right: auto;
      }
    }

    .copyright {
      font-size: 0.8rem;
      color: #757d6f;
    }
  }

  .top-link {
    color: #eeead7 !important;
    font-weight: 600;
  }
}
</style>
