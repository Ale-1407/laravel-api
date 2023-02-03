<template>
    <div>
        <div>
            <!-- loader -->
            <LoaderComp v-if="isLoading" />
            <!-- se la lunghezza è maggiore di 0 allora visualizzerò i post  -->
            <ul v-else-if="posts.length">
                <li v-for="elem in posts" :key="elem.id">{{ elem.title }}</li>
            </ul>
            <p v-else>Non sono presenti post</p>
        </div>
    </div>
</template>

<script>

import LoaderComp from '../LoaderComp.vue';

  export default{
    name: 'PostList',
    components:{
        LoaderComp
    },
    props: ['posts', 'isLoading']
  }
</script>



