<template>
    <div class="p-4">
        
        <div class="flex flex-wrap -mx-4 h-screen">
            <div class="flex flex-wrap w-full lg:w-2/3 px-4 content-start">
                <div class="w-full flex flex-wrap justify-center">
                    <div class="w-2/5 md:w-3/5 lg:w-1/3 p-0 md:p-4 mb-6 lg:mb-0 text-white">
                        <logo class="svg_logo " />
                    </div>
                    <counter />
                </div>
                <div class="w-full flex flex-wrap mt-8 ">
                    <spain />
                    <country-details :iso="selectedCountry" v-if="showChart" />
                </div>
                <world-map :iso="selectedCountry" />
            </div>
            <div class="w-full lg:w-1/3 px-4 mt-8 lg:mt-0">
                <countries-list @country="changeCountry" class="" />
            </div>
        </div>
        <links />
        <help />
    </div>
</template>

<script>
import Vue from 'vue'

import Logo from "@/assets/logo.svg";

import Counter from '@/components/Counter.vue'
// import Countries from '@/components/Countries.vue'
import CountriesList from '@/components/CountriesList.vue'
import CountryDetails from '@/components/CountryDetails.vue'
import Mapa from '@/components/Map.vue'
import Spain from '@/components/Spain.vue'
import Links from '@/components/Links.vue'
import Help from '@/components/Help.vue'

import 'vue-loaders/dist/vue-loaders.css'
import VueLoaders from 'vue-loaders'
Vue.use(VueLoaders);

export default {
    name: 'Home',
    components: {
        'counter': Counter,
        // 'countries': Countries,
        'countries-list': CountriesList,
        'country-details': CountryDetails,
        'spain': Spain,
        'world-map': Mapa,
        'logo': Logo,
        'links': Links,
        'help': Help
    },
    data: () => ({
        showChart: true,
        selectedCountry: 'es', 
    }),
    methods: {
        changeCountry(iso) {
            this.selectedCountry = iso
        }
    }, 
    mounted() {
        // this.$toasted.clear()      
        // this.$toasted.show("<div class='block'>Actualizado Hoy a las 18:20</div>", { 
        //     theme: "toasted-primary", 
        //     position: "top-center", 
        //     duration : 3000
        // });

    }
}
</script>
