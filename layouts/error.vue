<template>
    <div>
        <Nav class="fixed w-full"/>
        <div class="w-full h-screen flex justify-center items-center">
            <h1 v-if="error.statusCode === 404"
            class="text-3xl font-bold text-center text-gray-800">
            Halaman tidak ditemukan</h1>
        </div>
    </div>
</template>

<script>
  export default {
    props: ['error'],
    layout: 'empty',
  }
</script>