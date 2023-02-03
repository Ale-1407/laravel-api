<template>
    <div>
        <WorkComp />
        <!-- dati dei post -->
        <PostList :posts="posts" :isLoading="isLoading" />
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
            posts: [],
            isLoading: false
        }
    },
    mounted(){
        this.getPosts();
    },
    methods: {
        getPosts(){
            this.isLoading = true
            axios.get('http://localhost:8000/api/posts')
            .then( res => {
                console.log(res.data);
                this.posts = res.data
            }).catch(err => {
                console.log(err)
            }).then( () => {
                this.isLoading = false
            })
        }
    }
}
</script>

<style lang="scss">

</style>
