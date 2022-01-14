<template>
  <div>
      <div class="navbar py-4 shadow-lg border-b-2 bg-white">
  
      <div class="flex-1 px-2 mx-2">
        <NuxtLink to="/">
          <div class="flex px-2 mx-2">
            <img src="@/assets/svg/yokstudy-book.svg" alt="logo" class="w-10 h-auto">
            <span class="text-4xl ml-2 mt-1">
                  Yokstudy 
            </span>
          </div> 
        </NuxtLink>

        <div class="items-stretch hidden lg:flex">
          <NuxtLink to="/learn" class="btn btn-ghost btn-sm rounded-btn">
                  Learn
          </NuxtLink> 
          <NuxtLink to="/blog" class="btn btn-ghost btn-sm rounded-btn">
                  Blog
          </NuxtLink> 
          <NuxtLink to="/about" class="btn btn-ghost btn-sm rounded-btn">
                  About
          </NuxtLink>
        </div>

      </div> 
      <div class="flex-none">
        <button class="btn btn-square btn-ghost">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-6 h-6 stroke-current">              
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path>            
          </svg>
        </button>
      </div> 
      <div class="flex-none">
        <button class="btn btn-square btn-ghost">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-6 h-6 stroke-current">             
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>             
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>