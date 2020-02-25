<template>
  <div class="about p-3">
    <h1>This is an about page</h1>
    <p v-if="buildTime">
      Vue pre-rendered this page at <b>{{ buildTime }}</b> (before the browser
      ever saw it).
    </p>
    <template v-else>
      <p>
        Vue generated this page client-side because you navigated here from
        another route on the same site.
      </p>
      <p>
        <a href="/about" class="text-blue-500">Refresh the page</a> to see the
        pre-rendered version.
      </p>
    </template>
    <p>
      The browser loaded this page at <b>{{ loadTime }}</b>.
    </p>
  </div>
</template>

<script>
export default {
  asyncData() {
    // Don't re-evaluate buildTime when the client loads this page in the
    // browser.
    if (!process.client) {
      return {
        buildTime: new Date()
      };
    }
  },
  // Vue evaluates data variables at page render time and again every time the
  // browser loads this page.
  data: function() {
    return {
      loadTime: new Date().toString()
    };
  }
};
</script>