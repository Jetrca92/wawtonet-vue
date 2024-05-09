<template>

    <nav class="navbar mb-3" role="navigation" aria-label="main navigation">

        <div class="navbar-brand">
            <a class="navbar-item" href="">
                <img alt="wawtonet logo" src="../assets/wawtonetlogo.png">
                <span class="ml-1">WAWTONET</span>
            </a>

            <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample" @click="toggleMobileMenu">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>

        <div id="navbarBasicExample" class="navbar-menu" :class="{'is-active': showMobileMenu}">
            
            <div class="navbar-start">
                <a class="navbar-item">
                    Avto oglasi
                </a>
                <a class="navbar-item">
                    Zadnjih 100
                </a>
                <a class="navbar-item">
                    Objavi oglas
                </a>
            </div>

            <div class="navbar-end">
                <div class="navbar-item">
                    <div class="buttons">
                        <a class="button is-primary">
                            <strong>Registracija</strong>
                        </a>
                        <a class="button is-light">
                            Prijava
                        </a>
                    </div>
                </div>
            </div>

        </div>

    </nav>

</template>

<script setup>
import { ref } from 'vue'
const showMobileMenu = ref(false)
const toggleMobileMenu = () => {
  showMobileMenu.value = !showMobileMenu.value
}
</script>