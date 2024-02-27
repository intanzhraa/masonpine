<template>
    <nav class="bg-green border-green dark:bg-green">
        <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
            <router-link to="/" class="flex items-center">
                <img src="https://www.wahoowaterworld.co.id/static/media/mason-pine.97901d929ae88b3a9ab4fe6db58a9e02.svg" class="h-8 mr-3" alt="Mason Pine Logo" />
                <!-- <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">Mason Pine Hotel</span> -->
            </router-link>
            <button data-collapse-toggle="navbar-default" type="button"
                class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-green-100 focus:outline-none focus:ring-2 focus:ring-green-200 dark:text-green-400 dark:hover:bg-green-700 dark:focus:ring-green-600"
                aria-controls="navbar-default" aria-expanded="false">
                <span class="sr-only">Open main menu</span>
                <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M1 1h15M1 7h15M1 13h15" />
                </svg>
            </button>
            <div v-if="isAuthenticated" class="flex md:order-2">
                <CartBadgeComponent/>

                <router-link to="/profil" type="button"
                    class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 text-center mr-3 md:mr-0 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                    Profil
                </router-link>
            </div>
            <div v-if="isAuthenticated" class="flex md:order-2">
                <button @click="logout" type="button"
                    class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 text-center mr-3 md:mr-0 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                    Logout
                </button>
            </div>
            <!-- <div v-else class="flex md:order-2">
                <router-link to="/login" type="button"
                    class="text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:outline-none focus:ring-gray-300 font-medium rounded-lg text-sm px-4 py-2 text-center mr-3 md:mr-0 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                    Login
                </router-link>
            </div> -->
            <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-green rounded-lg bg-green md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-green md:dark:bg-green dark:border-green">
                    <li>
                        <router-link to="/">Home</router-link>
                    </li>
                </ul>
            </div>
            <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
                    <li>
                        <router-link to="/kamar">Kamar</router-link>
                    </li>
                </ul>
            </div>
            <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
                    <li>
                        <router-link to="/fasilitas">Fasilitas</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';
import CartBadgeComponent from './CartBadgeComponent.vue';
export default {
    computed: {
        ...mapGetters('auth', ['isAuthenticated']),
    },
    methods: {
        ...mapActions('auth', ['logout']),
    },
    components: { CartBadgeComponent }
};
</script>