<template>
  <Scroll/>
  <footer v-if="$slidev.nav.currentPage !== 1 && $slidev.nav.currentPage !== $slidev.nav.total + 1" class="absolute bottom-0 right-2 text-gray-400"><br/><small><SlideCurrentNo/>/<SlidesTotal/></small><br/></footer>
</template>