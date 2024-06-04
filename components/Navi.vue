<template>
    
      <ContentNavigation v-slot="{ navigation }">
      
            <NuxtLink :to="link._path" v-for="link of navigation" :key="link._path">{{ link.title }}</NuxtLink>
     
      </ContentNavigation>
    
  </template>