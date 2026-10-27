<script setup lang="ts">
import { isOpen } from '@/assets/js/nav.ts'

const closeMenu = () => {
  isOpen.value = false
}
</script>

<template>
  <nav>
    <div class="nav-container" :class="{ open: isOpen }">
      <!-- Logo linked to Home -->
      <RouterLink to="/" class="logo-link" @click="closeMenu">
        <svg
          width="100"
          height="100"
          viewBox="0 0 300 300"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect x="178" y="21" width="45" height="45" fill="#E5E0DC" />
          <circle cx="101" cy="44" r="18" fill="#29B6FF" />
          <path
            d="M126 86H76L123.5 200.5C132.5 221.5 104 256 83 256C83 263.165 83.4997 278.591 83.5 282.996C148.271 282.364 162.023 236.453 171 218L224 86H177L150 151L126 86Z"
            fill="#29B6FF"
          />
        </svg>
      </RouterLink>

      <!-- Navigation Content -->
      <div class="nav-buttons-container">
        <div class="nav-buttons" @click="closeMenu">
          <slot></slot>
        </div>
      </div>

      <!-- Burger Toggle Button -->
      <button
        @click="isOpen = !isOpen"
        class="burger"
        :aria-expanded="isOpen"
        aria-label="Toggle navigation menu"
      >
        <span />
        <span />
        <span />
      </button>
    </div>
  </nav>

  <!-- Fullscreen Backdrop Blur for Mobile -->
  <Transition name="fade">
    <div v-if="isOpen" class="backdrop-overlay" @click="closeMenu"></div>
  </Transition>
</template>

<style lang="scss" scoped>
/* Fullscreen Backdrop when Mobile Menu is Open */
.backdrop-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  z-index: 90;
}

/* Transition for Backdrop */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  padding: 12px 20px;
  box-sizing: border-box;

  /* Glassmorphism Bar */
  background: rgba(28, 32, 26, 0.75);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);

  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    position: relative;

    .logo-link {
      display: inline-flex;
      text-decoration: none;

      svg {
        width: 42px;
        height: 42px;
        min-width: 42px;
        min-height: 42px;
        background: #121411;
        border-radius: 8px;
        padding: 4px;
        box-sizing: border-box;
        border: 1px solid rgba(255, 255, 255, 0.1);
        transition: transform 0.2s ease;

        &:hover {
          transform: scale(1.03);
        }
      }
    }

    .nav-buttons-container {
      flex: 1;

      @media (max-width: 768px) {
        position: absolute;
        top: 65px;
        left: 0;
        right: 0;
        width: 100%;
      }
    }

    .nav-buttons {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      gap: 15px;

      @media (max-width: 768px) {
        flex-direction: column;
        align-items: stretch;
        background: #232720;
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 12px;
        padding: 16px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);

        /* Off-canvas Animation */
        opacity: 0;
        transform: translateY(-12px) scale(0.98);
        transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
        pointer-events: none;
      }
    }

    /* Mobile Open State */
    &.open {
      .nav-buttons {
        opacity: 1;
        transform: translateY(0) scale(1);
        pointer-events: auto;
      }
    }

    /* Animated Burger Icon */
    .burger {
      display: none;

      @media (max-width: 768px) {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 32px;
        height: 22px;
        background: transparent;
        border: none;
        cursor: pointer;
        padding: 0;
        z-index: 101;

        span {
          width: 100%;
          height: 2px;
          background-color: #eeead7;
          border-radius: 2px;
          transition: all 0.25s ease-in-out;
          transform-origin: center;
        }
      }
    }

    &.open {
      .burger {
        span {
          &:nth-child(1) {
            transform: translateY(10px) rotate(45deg);
          }

          &:nth-child(2) {
            opacity: 0;
            transform: scaleX(0);
          }

          &:nth-child(3) {
            transform: translateY(-10px) rotate(-45deg);
          }
        }
      }
    }
  }
}
</style>
