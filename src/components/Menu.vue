<template>
  <ul class="navbar-nav ms-auto">
                <li class="nav-item">
                    <router-link>Gallery</router-link>
                </li>
                <li class="nav-item">
                    <router-link class="nav-link" to="/about">About</router-link>
                </li>
                <li class="nav-item">
                    <a class="nav-link" aria-current="page" href="https://www.instagram.com/nairazak.art/" target="_blank"><img src="../assets/instagram.svg" alt="Instagram logo"></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="https://www.artstation.com/nairazak" target="_blank"><img src="../assets/artstation.svg" alt="Artstation logo"></a>
                </li>
            </ul>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .nav-link {
        padding: 2px 2px 2px 2px;
        color:black!important;
        @media (prefers-color-scheme: dark) {
            color: black!important
        }
        img {
             @media (prefers-color-scheme: dark) {
            color: black!important
        }
        }
    }
</style>