<template>
  <div class="carousel-cell">
    <slot />
  </div>
</template>

<script>
import 'flickity/dist/flickity.css'
export default {
  name: 'FlickityCell',
  setup () {
    return {}
  }
}
</script>
