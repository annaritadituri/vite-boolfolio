<script>
    import axios from 'axios';
    export default {
        name: 'Projects',

        data() {

            return {
                title: 'Projects',
                projects: [],
            };

        },

        methods: {
            
            getProjects() {

                axios.get('http://127.0.0.1:8000/api/projects').then(response => {
                    
                    if (response.data.response) {
                        console.log(response.data.results);
                        this.projects = response.data.results;
                    } else {
                        console.log('non puoi accedere a questa risorsa');
                    }

                });

            }
        },

        created() {
            this.getProjects();
        }
    }
</script>

<template>
    <h1>{{ title }}</h1>
</template>

<style lang="scss" scoped>
</style>
