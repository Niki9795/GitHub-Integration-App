<!-- components/Navbar.vue -->

<template>
  <header class="leading-relaxed max-h-screen">
    <nav>
      <div class="mx-auto p-4 font-normal">
        <div class="no-underline text-blueviolet">

          <RouterLink 
            to="/" 
            class="transition duration-400 
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            Home
          </RouterLink>

          <RouterLink 
            to="/log in" 
            class="transition duration-400 
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            Log in
          </RouterLink>

          <RouterLink 
            to="/repos" 
            class="transition duration-400 
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            Repos
          </RouterLink>

          <RouterLink 
            to="/profile" 
            class="transition duration-400 
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            Profile
          </RouterLink>

          <RouterLink 
            to="/githubrepos" 
            class="transition duration-400
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            GitHub API Repos
          </RouterLink>

          <RouterLink 
            to="/githubgists" 
            class="transition duration-400
                   hover:bg-[hsla(281,26%,65%,0.2)]
                   mr-2">
            GitHub API Gist
          </RouterLink>

        </div>
      </div>
    </nav>
    <hr/>
  </header>

  <RouterView />
</template>
  
<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>