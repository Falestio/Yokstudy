<template>
    <div>
<!-- * Hero -->
    <div class="pb-16 pt-14 mb-16 w-full bg-base-200 flex justify-center xcontainer" id="hero">
        <div class="flex flex-col justify-center w-6/12 text-center">
            <img src="@/assets/svg/blog-hero-placeholder.svg" width="150" alt="" class="mb-6 mx-auto">
            <h1 class="text-4xl font-semibold mb-6">{{ article.title }}</h1>
            <p class="text-md">5 December 2021</p>
        </div>
    </div>

    <!-- * Content -->
    <div class="flex justify-between relative con">
        <!-- * TOC -->
        <div class="w-1/5 sticky top-0" id="blog-toc">
            <div class="border-r-2 border-gray-200 sticky top-8">
                <h3 class="text-md font-bold capitalize pl-2">Daftar konten</h3>
                <ul>
                    <li class="w-full py-2 pl-2 flex items-center hover:bg-base-300">Lorem ipsum dolor sit amet.</li>
                    <li class="w-full py-2 pl-2 flex items-center hover:bg-base-300">Lorem ipsum dolor sit amet Lorem, ipsum.</li>
                    <li class="w-full py-2 pl-2 flex items-center hover:bg-base-300">Lorem, ipsum dolor.</li>
                    <li class="w-full py-2 pl-2 flex items-center hover:bg-base-300">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolor, inventore.</li>
                    <li class="w-full py-2 pl-2 flex items-center hover:bg-base-300">Lorem ipsum dolor sit amet consectetur adipisicing elit.</li>
                </ul>
            </div>
        </div>

        <!-- * Article -->
        <article class="w-1/2" id="blog-article">
            <nuxt-content :document="article"/>
            <pre>{{ article }}</pre>
        </article>

        <!-- * Sidebar -->
        <aside class="w-1/5 sticky top-0" id="blog-sidebar">
            <div class="sticky top-8">
                <h3 class="text-md font-bold capitalize pl-2 mb-4">Share artikel ini</h3>
                <div class="flex gap-2 mb-8">
                    <i class="uil uil-instagram btn btn-square text-2xl btn-md"></i>
                    <i class="uil uil-facebook btn btn-square text-2xl btn-md"></i>
                    <i class="uil uil-whatsapp btn btn-square text-2xl btn-md"></i>
                    <i class="uil uil-twitter-alt btn btn-square text-2xl btn-md"></i>
                </div>

                <div class="bg-gray-300 w-full h-80"></div>
            </div>
        </aside>
    </div>
    </div>
</template>

<script>
export default {
  async asyncData ({ $content, app, params, error }) {
    // const path = params.slug
    const article = await $content('blog/' + params.post).fetch()
    console.log(params)
    if (!article) {
      return error({ statusCode: 404, message: 'Article not found' })
    } 

    return {
      article
    }
  }
}

</script>

<style>

</style>