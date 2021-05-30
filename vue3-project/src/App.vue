<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <router-link class="navbar-brand" to="/">
      To-Do Example
    </router-link>

    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
      <li class="nav-item">
        <router-link class="nav-link active" aria-current="page" to="/todos">
          Todos
        </router-link>
      </li>
    </ul>
  </nav>
  <router-view />
</template>

<script>
export default {};
</script>

<style scoped></style>
