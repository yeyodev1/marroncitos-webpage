<script setup lang="ts">
// Hero component refined with premium stock imagery and layered layout
</script>

<template>
  <section class="the-hero">
    <div class="hero-background">
      <img src="/Users/diegoreyes/.gemini/antigravity/brain/9779e9e2-913a-4412-b610-c1633fc9073d/marroncitos_stock_brownies_2_1774388509232.png" alt="Marroncitos Bakery" class="bg-image" />
      <div class="hero-overlay"></div>
    </div>

    <div class="hero-container">
      <div class="hero-grid">
        <div class="hero-content">
          <div class="badge">Artesanal & Premium</div>
          <h1 class="hero-title">
            El placer de un <br />
            <span class="highlight">Marroncito</span> perfecto
          </h1>
          <p class="hero-subtitle">
            Brownies melcochudos, tortas de autor y bocaditos que transforman cualquier momento en una celebración inolvidable.
          </p>
          <div class="hero-actions">
            <button class="btn btn-primary">Explorar Sabores</button>
            <button class="btn btn-outline">Nuestra Historia</button>
          </div>
        </div>

        <div class="hero-visual">
          <div class="floating-card">
            <img src="/Users/diegoreyes/.gemini/antigravity/brain/9779e9e2-913a-4412-b610-c1633fc9073d/marroncitos_stock_brownies_1_1774388494006.png" alt="Detail Brownie" class="detail-image" />
            <div class="card-tag">Receta Original</div>
          </div>
          <div class="experience-badge">
            <span class="number">100%</span>
            <span class="text">Chocolate <br /> Real</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.the-hero {
  position: relative;
  width: 100%;
  min-height: 90vh;
  display: flex;
  align-items: center;
  overflow: hidden;
  font-family: $font-principal;
  background-color: $primary-dark;

  .hero-background {
    position: absolute;
    inset: 0;
    z-index: 0;

    .bg-image {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: brightness(0.7);
    }

    .hero-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(
        90deg,
        rgba($primary-dark, 0.9) 0%,
        rgba($primary-dark, 0.6) 50%,
        rgba($primary-dark, 0.3) 100%
      );
    }
  }

  .hero-container {
    width: 100%;
    max-width: 1300px;
    margin: 0 auto;
    padding: 2rem 1.5rem 6rem;
    position: relative;
    z-index: 1;
  }

  .hero-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 4rem;
    align-items: center;

    @media (min-width: 1024px) {
      grid-template-columns: 1.2fr 0.8fr;
    }
  }

  .hero-content {
    animation: fadeInLeft 1.2s cubic-bezier(0.22, 1, 0.36, 1);

    .badge {
      display: inline-block;
      padding: 0.5rem 1.25rem;
      background-color: rgba($primary, 0.15);
      border: 1px solid rgba($primary, 0.3);
      color: $primary;
      border-radius: 100px;
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 2rem;
    }

    .hero-title {
      font-size: 3rem;
      font-weight: 900;
      line-height: 1.1;
      color: $white;
      margin-bottom: 1.5rem;

      @media (min-width: 768px) {
        font-size: 4.5rem;
      }

      .highlight {
        color: $primary;
        position: relative;
        display: inline-block;
        
        &::after {
          content: '';
          position: absolute;
          bottom: 10%;
          left: 0;
          width: 100%;
          height: 8px;
          background-color: rgba($primary, 0.2);
          z-index: -1;
        }
      }
    }

    .hero-subtitle {
      font-size: 1.1rem;
      color: rgba($white, 0.8);
      line-height: 1.6;
      margin-bottom: 3rem;
      max-width: 500px;
      font-family: $font-secondary;

      @media (min-width: 768px) {
        font-size: 1.35rem;
      }
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 1.25rem;

      .btn {
        padding: 1.1rem 2.5rem;
        border-radius: 100px;
        font-weight: 700;
        text-transform: uppercase;
        letter-spacing: 0.05em;
        font-size: 0.95rem;
        cursor: pointer;
        transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
        border: 2px solid transparent;

        &.btn-primary {
          background-color: $primary;
          color: $white;
          box-shadow: 0 10px 30px rgba($primary, 0.3);

          &:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba($primary, 0.5);
            background-color: lighten($primary, 5);
          }
        }

        &.btn-outline {
          background-color: transparent;
          border-color: rgba($white, 0.2);
          color: $white;

          &:hover {
            border-color: $white;
            background-color: rgba($white, 0.05);
            transform: translateY(-5px);
          }
        }
      }
    }
  }

  .hero-visual {
    position: relative;
    display: none;
    justify-content: center;
    animation: fadeInRight 1.5s cubic-bezier(0.22, 1, 0.36, 1);

    @media (min-width: 1024px) {
      display: flex;
    }

    .floating-card {
      position: relative;
      width: 380px;
      height: 480px;
      border-radius: 24px;
      overflow: hidden;
      box-shadow: 0 30px 60px rgba(0,0,0,0.5);
      border: 8px solid rgba($white, 0.1);
      transform: rotate(3deg);
      transition: transform 0.6s ease;

      &:hover {
        transform: rotate(0deg) scale(1.02);
      }

      .detail-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }

      .card-tag {
        position: absolute;
        bottom: 2rem;
        left: 2rem;
        background: rgba($primary-dark, 0.8);
        backdrop-filter: blur(10px);
        padding: 0.6rem 1.2rem;
        border-radius: 8px;
        color: $white;
        font-weight: 700;
        font-size: 0.9rem;
      }
    }

    .experience-badge {
      position: absolute;
      top: -2rem;
      right: -1rem;
      width: 120px;
      height: 120px;
      background-color: $primary;
      border-radius: 50%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: $white;
      box-shadow: 0 15px 30px rgba($primary, 0.4);
      z-index: 2;
      animation: float 4s ease-in-out infinite;

      .number {
        font-size: 1.5rem;
        font-weight: 900;
        line-height: 1;
      }

      .text {
        font-size: 0.7rem;
        font-weight: 700;
        text-transform: uppercase;
        text-align: center;
        letter-spacing: 0.1em;
        line-height: 1.2;
      }
    }
  }

}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-15px) rotate(5deg); }
}
</style>
