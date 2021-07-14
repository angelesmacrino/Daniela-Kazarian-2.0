<template>
<div class="lightbox" @click.self="closeLightbox">    
  <img :src="photoUrl(photo.filename)">    
    <div class="lightbox-info">
        <div class="lightbox-info-inner">
            {{photo.title}}
        </div>
    </div>  
</div>
</template>

<script>
import art from '@/art.json';
export default {
  name: 'Photo',
  data() {
    return {
      art,
    };
  },
  computed: {
    photo() {
      return this.art.find((photo) => {
        return photo.id === Number(this.$route.params.id);
      });
    },
  },
  methods: {
    photoUrl(filename) {
      return require(`../assets/images/${filename}`);
    },
    closeLightbox() {
      this.$router.push('/gallery');
    }
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
.lightbox {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(90, 90, 90, 0.8);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem;
    @include s-mobile {
      display:block;
    }
    @include mobile {
      display:block;
    }
    @include s-tablet {
      display:block;
    }
    img {
    margin: auto;
    width: 100%;
    grid-column-start: 2;
    @include mobile {
      margin: 3rem;
      width:85%
    }
    @include s-mobile {
      margin: 3rem;
      width:85%
    }
    @include s-tablet {
      margin: 3rem;
      width:85%
    }
  }
  .lightbox-info {
    margin: auto 2rem auto 0;
    .lightbox-info-inner {
    background-color: #FFFFFF;
    display: inline-block;
    padding: 2rem;
  }
  }
  }
</style>