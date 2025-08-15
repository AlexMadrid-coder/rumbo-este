<template>
    <nav class="navbar" :class="{ scrolled: isScrolled }">
        <div class="container">
            <!-- Aquí ponemos el nombre de la banda-->
            <div class="nav-container">
                <h3>RUMBO ESTE</h3>
            </div>
            <!-- Aquí ponemos toda la barra de navegaci´pn-->
             <ul class="nav-menu" :class="{ activate: isMenuOpen }">
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
              <div class="hamburguer" :class="{ active: isMenuOpen }" @click="toggleMenu"> 
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
}

</script>

<style scoped>
/* Estilos específicos para el componente de navegación */
</style>