<template>
    <v-container>
        <v-row>
            <Photo
                v-for="photo in photos"
                :key="photo.id"
                :photo="photo"
            />
        </v-row>
        
    </v-container>
</template>

<script>
import Photo from '@/components/photo/Photo.vue';


export default {
    data() {
        return {
            photos: []
        };
    },
    components: { Photo },
    mounted() {
        this.fetchToDo()
    },
    methods: {
        fetchToDo() {
            this.axios.get('https://jsonplaceholder.typicode.com/photos?_limit=10')
                .then(res => this.photos = res.data)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>