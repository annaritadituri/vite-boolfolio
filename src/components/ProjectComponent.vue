<script>
    export default {
        name: 'Project',
        props: ['title', 'description', 'start_date'],
    }
</script>

<template>

    <div class="card">
        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>
            <h6 class="card-subtitle mb-2 text-body-secondary">Start date: {{ start_date }}</h6>
            <p class="card-text">{{ description }}</p>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
</style>
