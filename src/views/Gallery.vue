<template>
  <div class="gallery m-5">
    <div class="gallery-panel" v-for="photo in art" :key="photo.id">
      <transition appear name="fade">
        <router-link :to="`/photo/${photo.id}`">
          <img :src="thumbUrl(photo.filename)">
        </router-link>
      </transition>
    </div>
  </div>
</template>

<script>
import art from '@/art.json';
export default {
  name: 'Gallery',
  data() {
    return {
      art,
    };
  },
  methods: {
    thumbUrl(filename) {
      return require(`../assets/images/${filename}`);
    },
  },
};
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


.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 1rem;
    @include s-mobile {
      grid-template-columns: repeat(2,1fr)
    }
    @include mobile {
      grid-template-columns: repeat(2,1fr)
    }
    @include s-tablet {
      grid-template-columns: repeat(2,1fr)
    }      
    .gallery-panel img {
    width: 100%;
    height: 22vw;
    object-fit: cover;
    border-radius: 0.25rem;
    @include mobile {
      height:100%
    }
    @include s-mobile {
      height:100%
    }
    @include s-tablet {
      height:100%
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