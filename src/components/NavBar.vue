<template>
  <nav class="navbar navbar-expand-sm navbar-light">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">Daniela Kazarian</a>
        <button @click="toggleNavBar" class="navbar-toggler" type="button" aria-controls="navbarSupportedContent" :aria-expanded="toggledNavBar" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <Menu/>
        </div>       
    </div>
    <transition name="mobileMenu" v-if="mobileView">
        <div class="d-flex flex-column-reverse align-items-center mt-0 shadow" id="navigation" v-if="toggledNavBar">
            <Menu/>
        </div>
    </transition>
</nav>
</template>

<script>
import Menu from "./Menu.vue"
export default {
    components: {
        Menu: Menu
    },
    data() {
        return {
            toggledNavBar: false,
            mobileView: false,
        }
    },
    methods: {
        toggleNavBar() {
            this.toggledNavBar = !this.toggledNavBar
        },
        handleView() {
          this.mobileView = window.innerWidth <= 700;
      }
    },
    created() {
      this.handleView();
      window.addEventListener('resize', this.handleView)
      console.log(this.mobileView)   

  }
}
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Yeon+Sung&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Stylish&display=swap');
$small-mobile-width: 320px;
$mobile-width: 600px;
 @mixin s-mobile {
      @media (max-width: #{$small-mobile-width}) {
        @content;
      }
    }

  @mixin mobile {
    @media (min-width: #{$small-mobile-width + 1px}) and (max-width: #{$mobile-width}) {
      @content;
    }
  }
    .navbar {
        background:white;
        @media (prefers-color-scheme: dark) {
            background:white;
        }
        .navbar-brand {
            font-family: "Yeon Sung", cursive;
            font-size:3.80rem;
            padding-left:5px;
            @include s-mobile {
                font-size:2.9rem ;
            }
        }
        .navbar-nav {
            font-family: 'Stylish', sans-serif;
            font-size:3rem;
            .nav-item {
                .nav-link {
                    color:black
                }
            }
        }
        .navbar-nav .mobile {
            position:absolute;
            .nav-item {
                width: max-content;
            }
        }
        .navbar-toggler {
            margin-right:20px;
        }
        #navigation {
            background: white;
            position:absolute;
            top:55px;
            right: 15px;
        }
    }
.mobileMenu-enter-from {
    transform: translateY(-300px);
}
.mobileMenu-enter-to {
    transform: translateY(1px);

}
.mobileMenu-enter-active {
    transition: all 1s 
}
.mobileMenu-leave-from {
    transform: translateY(0px);
}
.mobileMenu-leave-to {
    transform: translateY(-300px)
}
.mobileMenu-leave-active {
    transition: all 1s 
}

@media (prefers-color-scheme: dark) {
    .navbar-brand {
      color:black!important;
    }
}
</style>

