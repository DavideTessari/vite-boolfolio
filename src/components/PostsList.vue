<script>
import axios from 'axios';
import PostCard from './PostCard.vue';

export default {
    name: 'PostsList',
    data() {
        return {
            posts: []
        };
    },
    components: {
        PostCard
    },
    methods: {
        getPostsFromApi() {
            axios.get('http://127.0.0.1:8000/api/posts')
            .then((response) => {
                this.posts = response.data.results;
            });
        }
    },
    mounted() {
        this.getPostsFromApi();
    }
}
</script>

<template>
    <div class="container">
        <h1>All posts</h1>

        <div class="row row-cols-3">
            <div class="col" v-for="post in posts" :key="post.id">
                <PostCard :postInfo="post"></PostCard>
            </div>
        </div>
    </div>
</template>