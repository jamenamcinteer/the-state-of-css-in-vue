<template>
  <div>
    <nav class="navbar is-primary" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <div class="navbar-item">
          Random Corgi Images
        </div>
      </div>

      <div class="navbar-menu">
        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <a class="button is-primary" href="https://github.com/jamenamcinteer/the-state-of-css-in-vue/tree/master/example-projects/buefy" target="_blank">
                <strong>View on GitHub</strong>
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>
    <CorgiGrid />
  </div>
</template>

<script>
import CorgiGrid from './components/CorgiGrid.vue'

export default {
  name: 'App',
  components: {
    CorgiGrid
  }
}
</script>

<style lang="scss">
// Import Bulma's core
@import "~bulma/sass/utilities/_all";

// Set your colors
$primary: #34495e;
$primary-invert: findColorInvert($primary);
$secondary: rgb(221, 70, 0);
$secondary-invert: findColorInvert($secondary);
$navbar-background-color: #34495e;

// Setup $colors to use as bulma classes (e.g. 'is-primary')
$colors: (
    "primary": ($primary, $primary-invert),
    "secondary": ($secondary, $secondary-invert)
);

// Import Bulma and Buefy styles
@import "~bulma";
@import "~buefy/src/scss/buefy";
</style>
