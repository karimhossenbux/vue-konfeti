<template>
    <canvas></canvas>
</template>

<script>
import confetti from './confetti'

export default {
  name: 'VueConfetti',
  mounted: function () {
    this.$el.width = window.innerWidth
    this.$el.height = window.innerHeight
    confetti(this.$el).numberOfPieces(this.numberOfPieces)
      .friction(this.friction)
      .wind(this.wind)
      .gravity(this.gravity)
      .colors(this.colors)
      .opacity(this.opacity)
      .recycle(this.recycle)
      .run(this.run)()
  },
  props: {
    numberOfPieces: {
      type: Number,
      default: 200
    },
    friction: {
      type: Number,
      default: 0.99
    },
    wind: {
      type: Number,
      default: 0
    },
    gravity: {
      type: Number,
      default: 0.1
    },
    colors: {
      type: Array,
      default: function () {
        return ['#f44336', '#e91e63', '#9c27b0', '#673ab7', '#3f51b5',
        '#2196f3', '#03a9f4', '#00bcd4', '#009688', '#4CAF50',
        '#8BC34A', '#CDDC39', '#FFEB3B', '#FFC107', '#FF9800',
        '#FF5722', '#795548']
      }
    },
    opacity: {
      type: Number,
      default: 1.0
    },
    recycle: {
      type: Boolean,
      default: true
    },
    run: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style scoped>
  canvas {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    pointer-events: none;
    z-index: 1000;
  }
</style>
