<template>
    <div class="flex flex-col gap-8 my-8 con">
        <NuxtLink v-for="blog in blogs" :key="blog.slug" :to="'/blog/' + blog.slug">
            <div class="card lg:card-side bg-white border-2 border-gray-200 w-10/12 mx-auto rounded-md">
                <div class="card-body">
                    <h2 class="text-4xl font-bold mb-4">{{ blog.title }}</h2> 
                    <p>{{ blog.description }}</p> 
                </div>
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure> 
            </div>
        </NuxtLink>
    </div> 
</template>

<script>
export default {
    async asyncData ({ $content, app, params, error }) {
        const blogs = await $content('blog').sortBy('createdAt', 'desc').fetch()

        if (!blogs) {
            return error({ statusCode: 404, message: 'Article not found' })
        } 

        return {
            blogs
        }
    }
    }
</script>