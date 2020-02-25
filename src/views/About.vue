<template>
  <div class="about p-3">
    <h1>This is an about page</h1>
    <p>
      The browser loaded this page at
      <b>{{ loadTime }}</b>
    </p>
  </div>
</template>

<script>
export default {
  // Vue evaluates data variables at page render time and again every time the
  // browser loads this page.
  data: function() {
    return {
      loadTime: new Date().toString()
    };
  }
};
</script>
