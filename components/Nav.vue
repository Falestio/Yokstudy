<template>
  <div>
      <div class="navbar py-4 shadow-sm bg-white">
  
      <div class="flex-1 px-2 mx-2">
        <NuxtLink to="/"> 
          <div class="flex px-2 mx-2">
            <img src="@/assets/svg/yokstudy-book.svg" alt="logo" class="w-10 h-auto">
            <span class="text-4xl ml-2 mt-1 font-medium">
                  Yokstudy 
            </span>
          </div> 
        </NuxtLink>

        <div class="items-stretch hidden lg:flex">
          <NuxtLink to="/blog" class="btn btn-ghost btn-sm rounded-btn">
                  Blog
          </NuxtLink> 
          <NuxtLink to="/about" class="btn btn-ghost btn-sm rounded-btn">
                  About
          </NuxtLink>
        </div>

      </div> 
      <div class="flex-none">
          <div class="py-2 px-2 border-gray-200 border-2 rounded-md flex justify-center items-center gap-4 
                      cursor-pointer hover:bg-base-200 mr-8">
            <i class="uil uil-search"></i>
            <p>Cari Apa saja..</p>
            <kbd class="kbd kbd-xs">Ctrl + K</kbd>
          </div>
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