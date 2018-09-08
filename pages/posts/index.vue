<template>
    <p>{{ posts }}</p>
</template>

<script>
    import axios from 'axios'

    export default {
        data () {
            return {
                posts: []
            }
        },// if we prefix this method with async instead of returning a promise we can wait for this to finish and then return the data
        async asyncData () {
            // allows us to make a request and then go ahead and return an array which will be automatically assinged to the data that you would usually have defined in the data method
            let response = await axios.get('https://jsonplaceholder.typicode.com/posts')
                return {
                    posts : response.data
                }
        }
    }
</script>