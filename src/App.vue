<script>
    import axios from 'axios';
    import Project from './components/ProjectComponent.vue';
    export default {
        name: 'Projects',
        components: {
            Project
        },

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

    <div class="container">

        <h1 class="text-center">{{ title }}</h1>
        <div class="row">

            <div class="col-3" v-for="project in projects">
                <Project
                    :title="project.title"
                    :description="project.description"
                    :start_date="project.start_date"
                />
            </div>
                
        </div>

    </div>
    
</template>

<style lang="scss" scoped>
</style>
