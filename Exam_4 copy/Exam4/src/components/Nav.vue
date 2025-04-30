<script>
export default {
    data() {
        return {
            searchName: ''
        }
    },
    methods: {
        search() {
            this.$emit('search-pet', this.searchName);
        }
    }
}
</script>

<template>
    <nav>
        <router-link to="/">Home</router-link>
        <router-link to ="/pets">Pets</router-link>

        <div>
            <input v-model="searchName" type="text" placeholder="Enter a pet name" />
            <button @click="search">Search</button>
        </div>
    </nav>
</template>