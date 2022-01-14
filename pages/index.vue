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
                <div class="p-4 rounded-lg bg-gray-50 shadow-lg">
                    <ul class="home__list-of-subject">
                        <a href="#"><li>Sistem dan Sifat Periodik</li></a>
                        <a href="#"><li>Struktur Atom</li></a>
                        <a href="#"><li>Ikatan Kimia</li></a>
                        <a href="#"><li>Larutan Elektrolit dan non Elektrolit</li></a>
                        <a href="#"><li>Reaksi Redoks</li></a>
                        <a href="#"><li>Tata Senyawa dan persamaan reaksi</li></a>
                        <a href="#"><li>Stoikiometri</li></a>
                    </ul>
                </div>
                <div class="p-4 rounded-lg bg-gray-50 shadow-lg">
                    <ul class="home__list-of-subject">
                        <a href="#"><li>Termokimia</li></a>
                        <a href="#"><li>Laju Reaksi</li></a>
                        <a href="#"><li>Kesetimbangan Kimia</li></a>
                        <a href="#"><li>Larutan Asam Basa</li></a>
                        <a href="#"><li>Titrasi Asam Basa</li></a>
                        <a href="#"><li>Larutan Buffer</li></a>
                        <a href="#"><li>Hidrolisis Garam</li></a>
                        <a href="#"><li>Kelarutan Garam (KSP)</li></a>
                    </ul>
                </div>
                <div class="p-4 rounded-lg bg-gray-50 shadow-lg">
                    <ul class="home__list-of-subject">
                        <a href="#"><li>Sifat Koligatif Larutan</li></a>
                        <a href="#"><li>Redoks dan Elektrokimi</li></a>
                        <a href="#"><li>Reaksi Elektrolisis dan Hukum Faraday</li></a>
                        <a href="#"><li>Unsur-Unsur Utama</li></a>
                        <a href="#"><li>Unsur Transisi</li></a>
                        <a href="#"><li>Unsur Radioaktif</li></a>
                        <a href="#"><li>Senyawa Karbon</li></a>
                        <a href="#"><li>Benzena</li></a>
                        <a href="#"><li>Makromolekul</li></a>
                        <a href="#"><li>Biomolekul</li></a>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section id="blog" class="section">
        <div class="grid grid-cols-3 gap-8 con">
            <div class="card shadow-lg rounded-lg">
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure>
                <div class="card-body bg-gray-50">
                    <h2 class="card-title">Banyak Teknik belajar, mana yang paling bagus?</h2>
                    <p>Rerum reiciendis beatae tenetur excepturi aut pariatur est eos. Sit sit necessitatibus veritatis sed molestiae voluptates incidunt iure sapiente.</p>
                    <div class="card-actions">
                        <button class="btn btn-primary">More info</button>
                    </div>
                </div>
            </div>
            <div class="card shadow-lg rounded-lg">
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure>
                <div class="card-body bg-gray-50">
                    <h2 class="card-title">Blooms Taxonomy: teknik belajar solusi HOTS</h2>
                    <p>Rerum reiciendis beatae tenetur excepturi aut pariatur est eos. Sit sit necessitatibus veritatis sed molestiae voluptates incidunt iure sapiente.</p>
                    <div class="card-actions">
                        <button class="btn btn-primary">More info</button>
                    </div>
                </div>
            </div>
            <div class="card shadow-lg rounded-lg">
                <figure>
                    <img src="https://picsum.photos/id/1005/400/250">
                </figure>
                <div class="card-body bg-gray-50">
                    <h2 class="card-title">Memunculkan motivasi belajar dalam diri Anda</h2>
                    <p>Rerum reiciendis beatae tenetur excepturi aut pariatur est eos. Sit sit necessitatibus veritatis sed molestiae voluptates incidunt iure sapiente.</p>
                    <div class="card-actions">
                        <button class="btn btn-primary">More info</button>
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
}
</script>
