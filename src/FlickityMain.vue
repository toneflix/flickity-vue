<template>
  <div
    :ref="e=>mainRef=e"
    class="main-carousel"
    :class="'carousel'+key"
  >
    <slot flickity="flickity" />
  </div>
</template>

<script>
import { nextTick, onMounted } from 'vue'
import { onBeforeUnmount, watch, ref } from 'vue'

import Flickity from 'flickity'
export default {
  name: 'FlickityMain',
  emits: ['slideChange', 'ready', 'select', 'settle', 'staticClick', 'cellSelect', 'lazyLoad', 'scroll', 'dragStart', 'dragMove', 'dragEnd', 'pointerDown', 'pointerMove', 'pointerUp', 'select', 'settle', 'staticClick', 'cellSelect', 'lazyLoad', 'scroll', 'dragStart', 'dragMove', 'dragEnd', 'pointerDown', 'pointerMove', 'pointerUp'],
  props: {
    /**
     * The options to pass to the Flickity instance
     * @see https://flickity.metafizzy.co/options.html
     * @type {Object}
     */
    options: {
      type: Object,
      default: () => ({})
    },
    /**
     * The interval to auto play the carousel
     * @type {Number | Boolean}
     */
    autoplay: {
      type: [Boolean, Number],
      default: 5000,
    },
    /**
     * Whether to show the previous and next buttons
     * @type {Boolean}
     */
    prevNextButtons: {
      type: Boolean,
      default: false,
    },
    /**
     * Whether to show the page dots
     * @type {Boolean}
     */
    pageDots: {
      type: Boolean,
      default: false,
    },
    /**
     * Weather to enable the wrap around feature
     * @type {Boolean}
     */
    wrapAround: {
      type: Boolean,
      default: true,
    },
    /**
     * Weather to enable the adaptive height feature
     * @type {Boolean}
     */
    adaptiveHeight: {
      type: Boolean,
      default: true,
    },
    /**
     * Weather to enable the fade feature
     * @type {Boolean}
     */
    fade: {
      type: Boolean,
      default: false,
    },
    /**
     * How to align the cells in the carousel
     * @type {String}
     */
    cellAlign: {
      type: String,
      default: 'center',
    },
  },
  setup (props, { emit }) {
    let carousel = null,
      key = ref(Math.floor(Math.random() * 9000))
    mainRef = ref(null),
      options = Object.assign({
        cellAlign: props.cellAlign,
        adaptiveHeight: props.adaptiveHeight,
        fade: props.fade,
        wrapAround: props.wrapAround,
        pageDots: props.pageDots,
        prevNextButtons: props.prevNextButtons,
        autoPlay: props.autoplay,
        on: {
          ready: () => {
            emit('ready')
          }
        }
        // Merge the options with the default options
      });

    const initCarousel = () => {
      // key.value = Math.floor(Math.random() * 9000)
      // Create the carousel
      // carousel = new Flickity('.main-carousel.carousel' + key.value, options, props.options)
      carousel = new Flickity('.main-carousel', options, props.options)

      // Listen for slide change
      carousel.on('change', (index) => {
        emit('slideChange', index)
      });

      // Listen for slide change
      carousel.on('slideChange', (index) => {
        emit('slideChange', index)
      });

      // Listen for slide select
      carousel.on('select', (index) => {
        emit('select', index)
      });

      // Listen for slide scroll
      carousel.on('scroll', (progress) => {
        emit('scroll', progress)
      });

      // Listen for slide settle
      carousel.on('settle', (index) => {
        emit('settle', index)
      });

      // Listen for slide dragStart
      carousel.on('dragStart', (event, pointer) => {
        emit('dragStart', event, pointer)
      });

      // Listen for slide dragMove
      carousel.on('dragMove', (event, pointer, moveVector) => {
        emit('dragMove', event, pointer, moveVector)
      });

      // Listen for slide dragEnd
      carousel.on('dragEnd', (event, pointer) => {
        emit('dragEnd', event, pointer)
      });

      // Listen for slide pointerDown
      carousel.on('pointerDown', (event, pointer) => {
        emit('pointerDown', event, pointer)
      });

      // Listen for slide pointerMove
      carousel.on('pointerMove', (event, pointer, moveVector) => {
        emit('pointerMove', event, pointer, moveVector)
      });

      // Listen for slide pointerUp
      carousel.on('pointerUp', (event, pointer) => {
        emit('pointerUp', event, pointer)
      });

      // Listen for slide staticClick
      carousel.on('staticClick', (event, pointer, cellElement, cellIndex) => {
        emit('staticClick', event, pointer, cellElement, cellIndex)
      });

      // Listen for slide lazyLoad
      carousel.on('lazyLoad', (event, cellElement) => {
        emit('lazyLoad', event, cellElement)
      });

      // Listen for slide bgLazyLoad
      carousel.on('bgLazyLoad', (event, element) => {
        emit('bgLazyLoad', event, element)
      });

      // Listen for slide fullscreenChange
      carousel.on('fullscreenChange', (isFullscreen) => {
        emit('fullscreenChange', isFullscreen)
      });
    }

    nextTick(() => {
      initCarousel()
    })

    onBeforeUnmount(() => {
      // const carousel = new Flickity('.main-carousel.carousel' + key)
      carousel.destroy()
    })

    // onMounted(() => {
    //   // carousel = new Flickity('.main-carousel')
    //   // carousel.resize()
    //   if (!carousel) {
    //     initCarousel()
    //     carousel.resize()
    //   } else {
    //     carousel.reloadCells()
    //     carousel.resize()
    //   }
    // })

    return {
      key,
      mainRef,
      instance: carousel,
      Flickity,
      initCarousel,
      next () {
        carousel.next()
      },
      previous () {
        carousel.previous()
      },
      select (index) {
        carousel.select(index)
      },
      selectCell (index) {
        carousel.selectCell(index)
      },
      getSelectedIndex () {
        return carousel.selectedIndex
      },
      getSelectedElement () {
        return carousel.selectedElement
      },
      getCellElements () {
        return carousel.getCellElements()
      },
      getCellElement (index) {
        return carousel.getCellElement(index)
      },
      resize () {
        carousel.resize()
      },
      reposition () {
        carousel.reposition()
      },
      reloadCells () {
        carousel.reloadCells()
      },
      destroy () {
        carousel.destroy()
      },
      playPlayer () {
        carousel.playPlayer()
      },
      stopPlayer () {
        carousel.stopPlayer()
      },
      setPlayer (time) {
        carousel.setPlayer(time)
      },
      exitFullscreen () {
        carousel.exitFullscreen()
      },
      toggleFullscreen () {
        carousel.toggleFullscreen()
      },
      viewFullscreen () {
        carousel.viewFullscreen()
      },
    }
  },
}
</script>
