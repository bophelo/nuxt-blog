<template>
    <div>
        <template v-if="error.statusCode === 404">
            <h1>404</h1>
            <p>That page could not be found.</p>
            {{ error }}
        </template>
    </div>
</template>

<script>
    export default {
        props: ['error']
    }
</script>
