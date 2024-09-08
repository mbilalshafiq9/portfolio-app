<script setup lang="ts">
import Sidebar from '~/components/sidebar.vue';
</script>


<template>

    <main>
        <NuxtLoadingIndicator />
        <Sidebar />
        <div class="main-content">
          <Navbar />
          <slot />
        </div>

    </main>
</template>