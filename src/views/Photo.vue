<template>
  <Gallery />
  <Photo />
</template>
<script>
import Photo from '@/components/Photo.vue';
import Gallery from '@/views/Gallery.vue';

export default {
  name: 'photo',
  components: {
    Photo,
    Gallery
  },
};
</script>

