<template>
<div>
 <div class="rounded-lg shadow bg-base-200 drawer drawer-mobile max-h-max top-24">

    <input id="my-drawer-2" type="checkbox" class="drawer-toggle" />

    <!-- // * Content -->
    <div class="drawer-content p-8">
      <article id="learn-article">
        <h1 class="text-4xl">{{ article.title }}</h1>
        <nuxt-content :document="article"/>
      </article>
      <label for="my-drawer-2" class="absolute bottom-4 left-4 btn btn-green-400 btn-circle drawer-button lg:hidden"><i class="uil uil-angle-double-right icon"></i></label> 
    </div>

    <!-- Drawer -->
    <div class="drawer-side">

      <!-- Drawer Closer -->
      <label for="my-drawer-2" class="drawer-overlay"></label>

      <!-- Drawer Content -->
      <ul class="menu p-4 overflow-y-auto w-80 bg-base-100 text-base-content">

        <!-- Drawer Home Button and Dropdown  -->
        <div class="dropdown dropdown-hover mt-4 w-full">

          <!-- Drawer Home Button and Menu Button-->
          <div class="flex justify-between">
            <NuxtLink to="/" class="flex px-2 mx-2"> 
                <img src="@/assets/svg/yokstudy-book.svg" alt="logo" class="w-10 h-auto">
                <span class="text-4xl ml-2 mt-1 font-medium">
                      Yokstudy 
                </span>
            </NuxtLink>
            <div tabindex="0" class="bg-white mx-auto text-black shadow-sm flex items-center">
              <i class="uil uil-list-ul icon"></i>
            </div> 
          </div>

          <!-- Drawer Menu Dropdown -->
          <ul tabindex="0" class="p-2 shadow-lg menu dropdown-content bg-base-100 rounded-box w-72">
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

        <h3 class="text-md font-bold capitalize pl-5 pt-5 md-4">Kelas 10</h3>
        <li v-for="article in kimia10" :key="article.slug">
          <NuxtLink :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
        </li>

        <h3 class="text-md font-bold capitalize pl-5 pt-5 md-4">Kelas 11</h3>
        <li v-for="article in kimia11" :key="article.slug">
          <NuxtLink :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
        </li>

        <h3 class="text-md font-bold capitalize pl-5 pt-5 md-4">Kelas 12</h3>
        <li v-for="article in kimia12" :key="article.slug">
          <NuxtLink :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</div>

</template>

<script>
export default {
  layout: 'empty',

  async asyncData ({ $content, app, params, error }) {
    const article = await $content('kimia/' + params.slug).fetch()
    const kimia10 = await $content('kimia').where({ kelas: 10 }).fetch()
    const kimia11 = await $content('kimia').where({ kelas: 11 }).fetch()
    const kimia12 = await $content('kimia').where({ kelas: 12 }).fetch()

    if (!article) {
      return error({ statusCode: 404, message: 'Article not found' })
    }

    return {
      article, kimia10, kimia11, kimia12
    }
  }
    
  }
</script>

<style scoped>
#learn-article {
  max-width: 980px;
}

.nuxt-link-exact-active {
    color: green;
}
</style>