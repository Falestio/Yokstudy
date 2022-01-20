<template>
    
    <footer class="p-10 footer footer-center bg-green-50">
        <div>
            <a href="#" class="btn btn-block bg-pink-400">Support Yokstudy</a>
            <NuxtLink to="/about" class="btn btn-ghost btn-sm rounded-btn">
                Tentang kami
            </NuxtLink>
        </div> 
        <div class="grid grid-flow-col gap-4">
          <NuxtLink to="/kimia" class="btn btn-ghost btn-sm rounded-btn">
                  Kimia
          </NuxtLink>
          <NuxtLink to="/blog" class="btn btn-ghost btn-sm rounded-btn">
                  Blog
          </NuxtLink> 
        </div> 
        <div>
            <p>Copyright © 2022 - All right reserved Yokstudy</p>
        </div>
    </footer>
</template>

<script>
export default {
    
}
</script>