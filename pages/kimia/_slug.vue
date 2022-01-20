<template>
  <div class="rounded-lg shadow bg-base-200 drawer drawer-mobile max-h-max">
    <input id="my-drawer-2" type="checkbox" class="drawer-toggle" />
    <div class="drawer-content p-8">
      <article id="learn-article">
        <h1 class="text-4xl">{{ article.title }}</h1>
        <nuxt-content :document="article"/>
      </article>
    </div>
    <div class="drawer-side">
      <label for="my-drawer-2" class="drawer-overlay"></label>
      <ul class="menu p-4 overflow-y-auto w-80 bg-base-100 text-base-content">
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
</template>

<script>
export default {
  layout: 'NoFooter',

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