<template>
  <div>
<h1>Home</h1>
<ContentList :query="listing" v-slot="{ list }">
      <NuxtLink :to="article._path" v-for="article in list" :key="article._path">
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
      </NuxtLink>
    </ContentList>

</div>
</template>

<script setup lang="ts">
import type { QueryBuilderParams } from '@nuxt/content/dist/runtime/types'
const listing: QueryBuilderParams = { path: '/article', where: [{ _partial: false }], limit: 5, sort: [{ date: -1 }] }
</script>