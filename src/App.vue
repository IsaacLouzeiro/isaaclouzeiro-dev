<template>
    <div>
        <NavbarContent :language="language" @change-to="changeLang = $event" />
        
        <router-view/>
    </div>
</template>

<script>
import NavbarContent from '@/components/NavbarContent.vue'

export default {
    name: 'App',
    data() {
        return {
            language: [
                { name: 'English', isCheck: true },
                { name: 'Portuguese', isCheck: false }
            ],
            changeLang: ''
        }
    },
    components: {
        NavbarContent
    },
    watch: {
        changeLang(toLang) {
            console.log(toLang)
            if(toLang == 'Portuguese') {
                this.language[0].isCheck = false
                this.language[1].isCheck = true
            }else {
                this.language[0].isCheck = true
                this.language[1].isCheck = false
            }
        }
    }
}
</script>


<style lang="scss">
    // standard
    
    @import url('https://fonts.googleapis.com/css2?family=Ubuntu:ital,wght@0,300;0,500;0,700;1,300;1,400;1,500;1,700&display=swap'); // ubuntu font
    @import '@/assets/colors/colors.scss'; // colors

    .gradient { background-image: linear-gradient(to bottom right, $color-d-2, $color-l-2) } // main gradient

    a { &:hover { text-decoration: none; opacity: .7 } }; // link hover
    ul { list-style-type: none; } // list without style type
    .btn, button, input { &:focus, &:hover { border-color: rgba(0,0,0,0); outline: none; } } // removing outline

    * { // space and font
        margin: 0;
        padding: 0;
        font-family: 'Ubuntu', 'Trebuchet MS', sans-serif;
    }

    html, body { width: 100%; height: 100%; }

    #app {
        padding: 1rem;
    }

</style>
