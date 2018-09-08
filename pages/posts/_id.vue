<template>
    <div>
        <post :post="post"></post>
    </div>
</template>

<script>
    import axios from 'axios'

    import Post from '@/components/Post'

    export default {
        data () {
            return {
                post: null
            }
        },
        components: {
            Post
        },
        async asyncData ( { params }) {
            let response = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
                return {
                    post : response.data
                }
        }
    }
</script>