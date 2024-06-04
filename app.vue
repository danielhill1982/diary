<template>
  <div>

    <nav>
      <NuxtLink to="/">Home</NuxtLink>
      <ContentNavigation v-slot="{ navigation }">
        <NuxtLink v-for="link of navigation" :key="link._path" :to="link._path">
          {{ link.navTitle || link.title }}
        </NuxtLink>
      </ContentNavigation>
    </nav>

    <NuxtPage />

    <h1>Color mode: {{ $colorMode.value }}</h1>
    <select v-model="$colorMode.preference">
      <option value="system">System</option>
      <option value="light">Light</option>
      <option value="dark">Dark</option>
      <option value="sepia">Sepia</option>
    </select>
  </div>
</template>

<script setup>
const colorMode = useColorMode()

console.log(colorMode.preference)
</script>

<style>
body {
  background-color: #fff;
  color: rgba(0, 0, 0, 0.8);
}

.dark-mode body {
  background-color: #091a28;
  color: #ebf4f1;
}

.sepia-mode body {
  background-color: #f1e7d0;
  color: #433422;
}
</style>