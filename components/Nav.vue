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
      
      <NavSearchAlgolia/>

      <div class="dropdown dropdown-end lg:hidden">
        <div tabindex="0" class="m-1"><i class="uil uil-bars icon"></i></div> 
        <ul tabindex="0" class="p-2 shadow menu dropdown-content bg-base-100 rounded-box w-52">
          <li>
            <NuxtLink to="/blog" class="btn btn-ghost btn-sm rounded-btn">
                    Blog
            </NuxtLink> 
          </li> 
          <li>
            <NuxtLink to="/about" class="btn btn-ghost btn-sm rounded-btn">
                    About
            </NuxtLink>
          </li>
        </ul>
      </div>


    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>