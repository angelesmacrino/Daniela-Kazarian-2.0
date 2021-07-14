<template>
  <footer class="footer mt-auto">
    <small class="text-center">Copyright © 2021 Daniela Kazarian, all rights reserved. Design by Angeles Macrino</small>
</footer>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
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
    .footer {
        small {
            @include s-tablet {
                font-size: 1.2rem;
            }
            @include l-tablet {
                font-size: 1.8rem;
            }
            @include s-tablet {
               font-size: 1.8rem;
                }
            @include l-tablet {
                font-size: 1.8rem;
            }
            @include desktop {
                font-size: 1.8rem;
            }
            @include l-desktop {
                font-size: 1.8rem;
            }
                }
            }
</style>