<template>
    <div>
        <WorkComp />
        <!-- dati dei post -->
        <div>
            <ul>
                <li></li>
            </ul>
        </div>
    </div>
</template>


<script>
import WorkComp from '../components/WorkComp.vue';


export default {
    name: 'App',
    components: {
        WorkComp
    },
    mounted(){
        this.getPosts();
    },
    methods: {
        getPosts(){
            axios.get('http://localhost:8000/api/posts')
            .then( res => {
                console.log(res.data);
            })
        }
    }
}
</script>

<style lang="scss">

</style>
