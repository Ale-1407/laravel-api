<template>
    <div>
        <WorkComp />
        <!-- dati dei post -->
        <PostList :posts="posts" />
    </div>
</template>


<script>
import WorkComp from '../components/WorkComp.vue';
import PostList from '../components/posts/PostList.vue';

export default {
    name: 'App',
    components: {
        WorkComp,
        PostList
    },
    data(){
        return{
            posts: []
        }
    },
    mounted(){
        this.getPosts();
    },
    methods: {
        getPosts(){
            axios.get('http://localhost:8000/api/posts')
            .then( res => {
                console.log(res.data);
                this.posts = res.data
            })
        }
    }
}
</script>

<style lang="scss">

</style>
