<template>
    <div id="main">
        <HomeContent 
            :homeText="homeText" 
            :homeButtons="homeButtons" 
            :homeIsaac="homeIsaac" />
    </div>
</template>

<script>
import HomeContent from '@/components/HomeContent.vue';

export default {
    name: 'MainView',
    props: {
        // home content
        homeText: Array,
        homeButtons: Array,
        homeIsaac: Array
    },
    components: {
        HomeContent
    }
}
</script>
