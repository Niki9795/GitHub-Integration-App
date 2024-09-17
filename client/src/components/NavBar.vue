<template>
  <header class="leading-relaxed max-h-screen">
    <nav>
      <div class="mx-auto p-3 font-normal">
        <div class="flex items-center justify-between w-full text-blueviolet">
          <div class="flex items-center space-x-6">

            <RouterLink to="/">
              <img src="../assets/user.jpeg" class="h-12 w-12"/>
            </RouterLink>
            
            <RouterLink 
              to="/" 
              class="transition duration-500 
                    hover:bg-[hsla(281,26%,65%,0.2)]
                    font-semibold
                    p-1 rounded-md">
              Dashboard
            </RouterLink>
          </div>

          <div v-if="userData">
            <img :src="userData.avatar_url" class="h-8 w-8 rounded-full cursor-pointer" />
          </div>
          
        </div>
      </div>
    </nav>
    <hr/>
  </header>
  <RouterView />
</template>
  
<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { onMounted, ref } from 'vue';
import type { GithubUser} from '../APIsInterface'
import axios from 'axios';

let userData = ref<GithubUser>()

onMounted(async () => {
  console.log("Page 1 mounted")

  let userURL = 'http://localhost:5087/ghsecure/user'

  // Use axios to load the user data - read up on async/await to make
  // asynchronous calls easier
  let userAPI = await axios.get<GithubUser>(userURL)

  // If the request is successful (status 200), set the userData value
  if (userAPI.status === 200) {
    userData.value = userAPI.data
  }
})
</script>