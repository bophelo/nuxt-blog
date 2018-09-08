<template>
    <div>
        <h3>{{ pluralize('post', 2) }} </h3>
        <post v-for="post in posts" :key="post.id" :post="post"></post>
    </div>
</template>

<script>
    import axios from 'axios'
    import Post from '@/components/Post'

    export default {
        data () {
            return {
                posts: []
            }
        },// if we prefix this method with async instead of returning a promise we can wait for this to finish and then return the data
        layout: 'posts',
        head: {
            title: 'Posts'
        },
        components: {
            Post
        },
        async asyncData () {
            // allows us to make a request and then go ahead and return an array which will be automatically assinged to the data that you would usually have defined in the data method
            let response = await axios.get('https://jsonplaceholder.typicode.com/posts')
                return {
                    posts : response.data
                }
        }
    }
</script>