<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
#nav {
  @apply p-3;

  a {
    @apply text-blue-500 font-bold;

    &.router-link-exact-active {
      @apply text-black;
    }
  }
}
</style>
