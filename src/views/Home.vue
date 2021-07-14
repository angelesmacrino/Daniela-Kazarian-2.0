<template>
<transition appear name="fade">
  <div class="home">
    <img class="img-fluid mt-5" alt="Illustration of a white wherewolf with red eyes baring it`s teeth" src="../assets/images/Rage.jpg">
  </div>
</transition>
</template>

<script>
export default {
  name: 'Home',
  components: {
  }
}
</script>

<style scoped lang="scss">
  $small-mobile-width: 320px;
  $mobile-width: 600px;
  $tablet-width: 900px;
  $desktop-width: 1200px;
  $large-desktop-width: 1800px;

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
  @mixin s-tablet {
      @media (min-width: #{$mobile-width + 1px}) and (max-width: #{$tablet-width}) {
      @content;
    }
  }
  @mixin l-tablet {
      @media (min-width: #{$tablet-width + 1px}) and (max-width: #{$desktop-width}) {
      @content;
    }
  }
  @mixin desktop {
      @media (min-width: #{$desktop-width + 1px}) and (max-width: #{$large-desktop-width}) {
      @content;
    }
  }
  @mixin l-desktop {
      @media (min-width: #{$large-desktop-width + 1px}){
      @content;
    }
  }

.home {
  img {
    margin-top:10%;
    @include s-mobile {
      max-width:270px
    }
    @include mobile {
      max-width: 320px;
    }
    @include s-tablet {
      max-width: 580px;
    }
    @include l-tablet {
      max-width: 720px;
    }
    @include desktop {
      max-width: 520px;
    }
    @include l-desktop {
      max-width: 550px;
    }
  }
}
.fade-enter-from {
opacity: 0;
}
.fade-enter-to {
opacity:1
}

.fade-enter-active {
transition: all 2s ease
}
</style>
