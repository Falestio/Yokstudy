<template>
    <div>
        <div class="gcse-search" v-if="isSearchLoaded"></div>
    </div>
</template>

<script>
export default {
    data() {
        return {
        isSearchLoaded: true,
        }
    },

    head() {
        return {
        script: [
            {
                src: "https://cse.google.com/cse.js?cx=dcbe7c69fdaf8b8de",
                defer: true,
                // Changed after script load
                callback: () => {
                    this.isSearchLoaded = true;
                },
            },
        ],
        };
    },
};

</script>

<style scoped>
    .nuxt-content table, th, td {
        border: none !important;
    }

    .nuxt-content th,td {
        padding: 0 !important;
    }



</style>