<template>
    <div class="flex flex-col gap-8 mt-4">

        <div class="card lg:card-side card-bordered"  v-for="article in articles" :key="article.slug">
            <figure>
                <img src="https://picsum.photos/id/1005/400/250">
            </figure> 
            <div class="card-body">
                <h2 class="card-title">{{ article.title }}</h2> 
                <p>{{ article.description }}</p> 
            </div>
            <div class="card-actions">
                <button class="btn btn-primary">Get Started</button> 
                <button class="btn btn-ghost">More info</button>   
            </div>
        </div>
    </div> 
</template>

<script>
export default {
async asyncData ({ $content, app, params, error }) {
    // const path = params.slug
    const articles = await $content('blog').sortBy('createdAt', 'desc').fetch()

    if (!articles) {
        return error({ statusCode: 404, message: 'Article not found' })
    } 

    return {
        articles
    }
  }
}
</script>