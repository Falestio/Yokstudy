<template>
    <div>
        <h1>this is learn home page</h1>
    </div>
</template>

<script>
export default {
    async asyncData ({ $content, app, params, error }) {
        const article = await $content('kimia10/' + params.slug).fetch()
        if (!article) {
        return error({ statusCode: 404, message: 'Article not found' })
        }
        
        return {
            article
        }
    }
}
</script>