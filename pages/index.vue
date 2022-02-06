<template>
  <div>
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
        </div>
    </div>
      <section id="search" class="section">
        <div class="con flex flex-col gap-8">
            <h1 class="text-5xl text-center font-bold">Sumber belajar kimia dengan 103 artikel pembelajaran</h1>
            <div class="relative">
                <input type="text" placeholder="Cari materi kimia" class="w-full h-16 pr-16 input border-green-500 text-lg">
                <button class="absolute top-0 right-0 rounded-l-none btn bg-green-500 hover:bg-green-600 w-1/4 h-16 text-lg">cari</button>
            </div>
        </div>
    </section>

    <section id="content-list" class="section">
        <div class="con">
            <h1 class="text-4xl font-bold mb-4 pl-4">Kimia</h1>
            <div class="grid grid-cols-3 gap-8 text-lg">
                <!-- // * Kelas 10 -->
                <div class="p-4 rounded-lg bg-white shadow-lg">
                    <div class="flex flex-col gap-2">
                        <h3 class="text-lg font-bold p-2">Kelas10</h3>
                        <NuxtLink class="p-2 hover:bg-base-300 rounded-sm"
                         v-for="article in kimia10" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
                <!-- // * Kelas 11 -->
                <div class="p-4 rounded-lg bg-white shadow-lg">
                    <div class="flex flex-col gap-2">
                        <h3 class="text-lg font-bold p-2">Kelas11</h3>
                        <NuxtLink class="p-2 hover:bg-base-300 rounded-sm"
                        v-for="article in kimia11" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
                <!-- // * Kelas 12 -->
                <div class="p-4 rounded-lg bg-white shadow-lg">
                    <h3 class="text-lg font-bold p-2">Kelas12</h3>
                    <div class="flex flex-col gap-2">
                        <NuxtLink class="p-2 hover:bg-base-300 rounded-sm"
                        v-for="article in kimia12" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="blog" class="section">
        <div class="grid grid-cols-3 gap-8 con">
            <div class="card shadow-lg rounded-lg border-2 border-gray-100" v-for="post in blogs" :key="post.slug">
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure>
                <div class="card-body bg-white flex flex-col justify-between">
                    <div>
                        <h2 class="card-title">{{ post.title }}</h2>
                        <p>{{ post.description }}</p>
                    </div>
                    <div class="card-actions">
                        <NuxtLink class="btn bg-green-500 hover:bg-green-600" :to="'/blog/' + post.slug">Baca Selengkapnya</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <Footer/>

  </div>
</template>

<script>
export default {
    name: 'IndexPage',
    layout: 'empty',
    async asyncData ({ $content, app, params, error }) {
        const blogs = await $content('blog').sortBy('createdAt', 'desc').fetch()
        const kimia10 = await $content('kimia').where({ kelas: 10 }).fetch()
        const kimia11 = await $content('kimia').where({ kelas: 11 }).fetch()
        const kimia12 = await $content('kimia').where({ kelas: 12 }).fetch()

      return {
        kimia10, kimia11, kimia12, blogs
      }
    },
}
</script>
