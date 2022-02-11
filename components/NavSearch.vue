<template>
    <div>
        <div class="gcse-search p-10" v-if="isSearchLoaded"></div>
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




</style>