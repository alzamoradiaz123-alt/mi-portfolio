<template>
  <nav class="navbar navbar-expand-lg sticky-top">
    <div class="container nav-grid">

      <router-link class="brand" to="/">
        <img src="/logo_ba_no_fondo.png" alt="Bryan Alzamora" class="brand-logo" />
      </router-link>

      <div class="collapse navbar-collapse nav-center-wrap" id="navbarNav">
        <ul class="navbar-nav nav-center">
            <li class="nav-item">
                <router-link class="nav-link" to="/" active-class="active">Inicio</router-link>
            </li>
            <li class="nav-item">
                <router-link class="nav-link" to="/about" active-class="active">Sobre mí</router-link>
            </li>
            <li class="nav-item">
                <router-link class="nav-link" to="/contacto" active-class="active">Contacto</router-link>
            </li>

            <!-- Solo visible en móvil, dentro del menú desplegado -->
            <li class="nav-item d-lg-none mt-3">
                <span class="availability">
                <span class="dot"></span> Disponible para proyectos
                </span>
            </li>
            <li class="nav-item d-lg-none mt-2 mb-3">
                <router-link to="/contacto" class="btn-cta">¿Hablemos? →</router-link>
            </li>
        </ul>
      </div>

      <div class="nav-right d-none d-lg-flex align-items-center gap-3">
        <span class="availability">
          <span class="dot"></span> Disponible para proyectos
        </span>
        <router-link to="/contacto" class="btn-cta">¿Hablemos? →</router-link>
      </div>

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
        <span class="navbar-toggler-icon"></span>
      </button>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background-color: #FAFAFA !important;
  padding: 0.9rem 0;
  border: none;
  z-index: 1050;
  top: 0;        
}

.nav-grid {
  display: grid !important;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  column-gap: 24px;
}

/* --- Logo --- */
.brand {
  justify-self: start;
  display: flex;
  align-items: center;
  text-decoration: none;
  transition: opacity 0.25s;
}
.brand:hover {
  opacity: 0.7;
}

.brand-logo {
  height: 42px;  
  width: auto;
  display: block;
}

/* --- Nav centrado --- */
.nav-center-wrap {
  justify-self: center;
}
.nav-center {
  gap: 32px;
  align-items: center;
}

.nav-link {
  color: #6B6B6B !important;
  font-weight: 500;
  font-size: 0.95rem;
  padding: 4px 0 !important;
  position: relative;
  transition: color 0.25s, font-weight 0.25s;
}

.nav-link::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -4px;
  width: 100%;
  height: 2px;
  background: #6C4CF1;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.25s ease;
}

.nav-link:hover,
.nav-link.active {
  color: #111111 !important;
  font-weight: 700;
}
.nav-link:hover::after,
.nav-link.active::after {
  transform: scaleX(1);
}

/* --- CTA derecha --- */
.nav-right {
  justify-self: end;
}

.availability {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.85rem;
  color: #6B6B6B;
  white-space: nowrap;
}
.dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: #6C4CF1;
  animation: pulse 2s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.btn-cta {
  border: 1px solid #D8D8D8;
  color: #111111 !important;
  padding: 8px 18px;
  border-radius: 100px;
  font-weight: 500;
  font-size: 0.9rem;
  text-decoration: none;
  transition: border-color 0.3s, color 0.3s;
  white-space: nowrap;
}
.btn-cta:hover {
  border-color: #6C4CF1;
  color: #6C4CF1 !important;
}

/* --- Toggler móvil --- */
.navbar-toggler {
  border: 1px solid #EAEAEA;
  padding: 6px 10px;
  border-radius: 8px;
  background: transparent;
}
.navbar-toggler:focus {
  box-shadow: none;
  outline: none;
}
.navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba(17,17,17,1)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}

/* --- Responsive --- */
@media (max-width: 991px) {
  .nav-grid {
    grid-template-columns: 1fr auto;
  }

  .navbar-toggler {
    grid-column: 2;
    justify-self: end;
  }

  .nav-center-wrap {
    justify-self: stretch;
    grid-column: 1 / -1;
    margin-top: 1rem;
  }
  .nav-center {
    gap: 0;
    align-items: flex-start;
  }
  .nav-link {
    padding: 10px 0 !important;
    font-size: 1rem;
  }
  .nav-link::after {
    display: none;
  }

  .brand-logo {
    height: 36px;
  }
}
</style>