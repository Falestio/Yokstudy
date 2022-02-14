<template>
  <div>
    <label for="search-modal">
        <div class="flex-none">
            <div class="md:py-2 md:px-2 py-1 px-1 border-gray-200 border-2 rounded-md md:flex justify-center items-center gap-4 
                        cursor-pointer hover:bg-base-200 mr-8 hidden">
                <i class="uil uil-search"></i>
                <p>Cari Apa saja..</p>
                <kbd class="kbd kbd-xs">Ctrl + K</kbd>
            </div>
            <i class="uil uil-search md:hidden icon"></i>
        </div>
    </label> 
        <input type="checkbox" id="search-modal" class="modal-toggle" @click="showSearch()"> 
        <div class="modal">
            <div class="modal-box">
                <button class="btn" @click="hideSearch()">Close</button>
                <ais-instant-search index-name="test_yokstudy" :search-client="searchClient">
                    <ais-search-box
                     placeholder="Cari materi atau blog"
                     submit-title="Cari"
                     :autofocus="true"
                     :escapeHTML="false" />
                     <ais-infinite-hits />
                </ais-instant-search>
            </div>
        </div>
  </div>
</template>
<script>
import { AisInstantSearch, AisSearchBox, AisInfiniteHits } from 'vue-instantsearch';
import algoliasearch from 'algoliasearch/lite';

export default {
    data() {
      return {
        searchClient: algoliasearch(
          'F287JN255L',
          '56387c09941da524e6ea286c547aede3'
        ),

        searchBoxAutofocus: true,
      };
    },

    components: {
      AisInstantSearch,
      AisSearchBox,
      AisInfiniteHits,
    },

    methods: {
        showSearch() {
            document.getElementById("search-modal").checked = true;
        },
        hideSearch() {
            document.getElementById("search-modal").checked = false;
        },
    },

    mounted() {
        this._keyListener = function(e) {
            if (e.key === "k" && (e.ctrlKey || e.metaKey)) {
                e.preventDefault(); // present "Save Page" from getting triggered.

                this.showSearch();
            }
        };

        document.addEventListener('keydown', this._keyListener.bind(this));
    },

    beforeDestroy() {
        document.removeEventListener('keydown', this._keyListener);
    },
}
</script>

<style>

</style>