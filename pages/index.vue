<template>
  <div>
      <section id="search" class="section">
        <div class="con flex flex-col gap-8">
            <h1 class="text-5xl text-center font-bold">Sumber belajar kimia dengan 103 artikel pembelajaran</h1>
            <div class="relative">
                <input type="text" placeholder="Cari materi kimia" class="w-full h-16 pr-16 input input-primary text-lg">
                <button class="absolute top-0 right-0 rounded-l-none btn btn-primary w-1/4 h-16 text-lg">cari</button>
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
                        <NuxtLink v-for="article in kimia10" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
                <!-- // * Kelas 11 -->
                <div class="p-4 rounded-lg bg-white shadow-lg">
                    <div class="flex flex-col gap-2">
                        <NuxtLink v-for="article in kimia11" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
                <!-- // * Kelas 12 -->
                <div class="p-4 rounded-lg bg-white shadow-lg">
                    <div class="flex flex-col gap-2">
                        <NuxtLink v-for="article in kimia12" :key="article.slug" :to="'/kimia/' + article.slug">{{ article.title }}</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="blog" class="section">
        <div class="grid grid-cols-3 gap-8 con">
            <div class="card shadow-lg rounded-lg" v-for="post in blogs" :key="post.slug">
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure>
                <div class="card-body bg-gray-50">
                    <h2 class="card-title">{{ post.title }}</h2>
                    <p>{{ post.description }}</p>
                    <div class="card-actions">
                        <NuxtLink class="btn btn-primary" :to="'/blog/' + post.slug">Baca Selengkapnya</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </section>


  </div>
</template>

<script>
export default {
    name: 'IndexPage',
    layout: 'default',
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
