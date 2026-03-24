<script setup lang="ts">
import { computed } from 'vue';

const currentYear = computed(() => new Date().getFullYear());

const legalInfo = {
  razonSocial: 'HARISSALIMENTOS S.A.',
  ruc: '0992932058001',
  direccion: 'Calle Tercera 306 e Intersección Av. Central, Cdla. Miraflores, Guayaquil, Ecuador.',
  telefono: '+593 4 2001356',
  email: 'abarciona@gmail.com',
  representante: 'Adriana Paola Barciona Simon'
};
</script>

<template>
  <footer class="the-footer">
    <div class="footer-content">
      <div class="legal-section">
        <h3 class="section-title">Información Legal Obligatoria</h3>
        <div class="legal-grid">
          <div class="legal-item">
            <span class="label">Razón Social:</span>
            <span class="value">{{ legalInfo.razonSocial }}</span>
          </div>
          <div class="legal-item">
            <span class="label">RUC:</span>
            <span class="value">{{ legalInfo.ruc }}</span>
          </div>
          <div class="legal-item">
            <span class="label">Dirección:</span>
            <span class="value">{{ legalInfo.direccion }}</span>
          </div>
          <div class="legal-item">
            <span class="label">Teléfono:</span>
            <a :href="`tel:${legalInfo.telefono.replace(/\s+/g, '')}`" class="value link">{{ legalInfo.telefono }}</a>
          </div>
          <div class="legal-item">
            <span class="label">Correo electrónico:</span>
            <a :href="`mailto:${legalInfo.email}`" class="value link">{{ legalInfo.email }}</a>
          </div>
          <div class="legal-item">
            <span class="label">Representante Legal:</span>
            <span class="value">{{ legalInfo.representante }}</span>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} Marroncitos. Todos los derechos reservados.</p>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.the-footer {
  width: 100%;
  background-color: $primary-dark;
  color: $white;
  padding: 3rem 1.5rem 1.5rem;
  font-family: $font-principal;

  .footer-content {
    max-width: 1200px;
    margin: 0 auto;
  }

  .legal-section {
    margin-bottom: 2.5rem;

    .section-title {
      font-size: 1.1rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      margin-bottom: 1.5rem;
      color: $primary;
      opacity: 0.9;
    }

    .legal-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.25rem;

      @media (min-width: 768px) {
        grid-template-columns: repeat(2, 1fr);
      }

      @media (min-width: 1024px) {
        grid-template-columns: repeat(3, 1fr);
      }
    }

    .legal-item {
      display: flex;
      flex-direction: column;
      gap: 0.25rem;

      .label {
        font-size: 0.75rem;
        font-weight: 600;
        color: rgba($white, 0.6);
        text-transform: uppercase;
      }

      .value {
        font-size: 0.9rem;
        line-height: 1.4;

        &.link {
          color: $white;
          text-decoration: none;
          transition: color 0.3s ease;

          &:hover {
            color: $primary;
          }
        }
      }
    }
  }

  .footer-bottom {
    border-top: 1px solid rgba($white, 0.1);
    padding-top: 1.5rem;
    text-align: center;

    p {
      font-size: 0.8rem;
      color: rgba($white, 0.5);
    }
  }
}
</style>
