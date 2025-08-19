<template>
    <nav class="navbar" :class="{ scrolled: isScrolled }">
        <div class="container">
            <!-- Aquí ponemos el nombre de la banda-->
            <div class="nav-brand">
                <h3>RUMBO ESTE</h3>
            </div>
            <!-- Aquí ponemos toda la barra de navegaci´pn-->
             <ul class="nav-menu" :class="{ active: isMenuOpen }">
                <li class="nav-item"> 
                    <a href="#inicio" class="nav-link" @click="closeMenu">Inicio</a>
                </li>
                <li class="nav-item">
                    <a href="#musica" class="nav-link" @click="closeMenu">Música</a>
                </li>
                <li class="nav-item">
                    <a href="#banda" class="nav-link" @click="closeMenu">Banda</a>
                </li>
                <li class="nav-item">
                    <a href="#conciertos" class="nav-link" @click="closeMenu">Conciertos</a>
                </li>
                <li class="nav-item">
                    <a href="#contacto" class="nav-link" @click="closeMenu">Contacto</a>
                </li>
             </ul>
             <!-- Botón de hamburguesa para el diseño móvil-->
              <div class="hamburger" :class="{ active: isMenuOpen }" @click="toggleMenu"> 
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
              </div>
        </div>
    </nav>
</template>

<script>
export default {
  name: 'Navigation',
  data() {
    return {
        isMenuOpen: false,
        isScrolled: false
    }
  },
  methods: {
    toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll)
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll)
    },
    closeMenu() {
        this.isMenuOpen = false
    },
    handleScroll() {
        this.isScrolled = window.scrollY > 50
    }
  }
}


</script>

<style scoped>
/* Estilos específicos para el componente de navegación */
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background: rgba(107, 52, 41, 0.95);
  backdrop-filter: blur(20px);
  z-index: 1000;
  padding: 1rem 0;
  transition: var(--transition-medium);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand h3 {
  color: var(--cream);
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: 2px;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-link {
  color: var(--cream);
  text-decoration: none;
  font-weight: 500;
  transition: var(--transition-fast);
  position: relative;
}

.nav-link:hover {
  color: var(--accent-rose);
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--accent-rose);
  transition: var(--transition-fast);
}

.nav-link:hover::after {
  width: 100%;
}

/* Hamburger menu para móvil */
.hamburger {
  display: none;
  flex-direction: column;
  cursor: pointer;
}

.bar {
  width: 25px;
  height: 3px;
  background: var(--cream);
  margin: 3px 0;
  transition: var(--transition-fast);
}

/* Responsive */
@media screen and (max-width: 768px) {
  .hamburger {
    display: flex;
  }
  
  .nav-menu {
    position: fixed;
    left: -100%;
    top: 70px;
    flex-direction: column;
    background: var(--secondary-burgundy);
    width: 100%;
    text-align: center;
    transition: var(--transition-medium);
    padding: 2rem 0;
  }
  
  .nav-menu.active {
    left: 0;
  }
  
  .nav-item {
    margin: 1rem 0;
  }
}

</style>