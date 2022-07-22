<template>
    <div class="row h-100 g-0">
        <NavbarContent class="col-1" :language="language" :navBar="navBar" @change-to="changeLang = $event" />
        
        <router-view 
            class="col-sm-11 gx-sm-5"

            :homeText="homeText"    
            :homeButtons="homeButtons"    
            :homeIsaac="homeIsaac"    
        />
    </div>
</template>

<script>
import NavbarContent from '@/components/NavbarContent.vue'

export default {
    name: 'App',
    data() {
        return {
            // navbar content
            language: [],
            changeLang: '',
            navBar: [],

            // home content
            homeText: [],
            homeButtons: [],
            homeIsaac: []
        }
    },

    // translation config
    methods: {
        english() {
            // navbar content
            this.language = [
                { showName: 'English', name: 'English', isCheck: true },
                { showName: 'Portuguese', name: 'Portuguese', isCheck: false }
            ]

            this.navBar = [
                'Home',
                'About',
                'My Work',
                'Contact'
            ],

            // home content
            this.homeText = [ 
                "Welcome to my website.",
                "Recently my passion is creating websites. I'm very curious and constantly searching for new things to learn."
            ],

            this.homeButtons = [
                {
                    name: 'Web Resume',
                    link: 'https://isaac-resume.web.app/'
                },
                {
                    name: 'Codepen',
                    link: 'https://codepen.io/isaaclouzeiro'
                },
                {
                    name: 'Github',
                    link: 'https://github.com/IsaacLouzeiro'
                }
            ],

            this.homeIsaac = ['Isaac Louzeiro', 'Front-End Web Developer']
        },

        portuguese() {
            // navbar content
            this.language = [
                { showName: 'Inglês', name: 'English', isCheck: false },
                { showName: 'Português', name: 'Portuguese', isCheck: true }
            ]
            
            this.navBar = [
                'Início',
                'Sobre',
                'Meus Trabalhos',
                'Contato'
            ],

            // home content
            this.homeText = [ 
                "Bem vindo ao meu site.",
                "Recentemente minha paixão é criar sites. Eu sou bastante curioso e estou constantemente procurando coisas novas para aprender."
            ],

            this.homeButtons = [
                {
                    name: 'Currículo Web',
                    link: 'https://isaac-resume.web.app/'
                },
                {
                    name: 'Codepen',
                    link: 'https://codepen.io/isaaclouzeiro'
                },
                {
                    name: 'Github',
                    link: 'https://github.com/IsaacLouzeiro'
                }
            ],

            this.homeIsaac = ['Isaac Louzeiro', 'Desenvolvedor Web Front-End']
        }
    },
    created() {
        this.english()
    },
    components: {
        NavbarContent
    },
    watch: {
        changeLang(toLang) {
            // console.log(toLang)
            if(toLang == 'Portuguese') {
                this.portuguese()
            }else {
                this.english()
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
        box-sizing: border-box;
    }

    html, body, #app { width: 100%; height: 100%; }

    #app {
        padding: 1rem;
        position: relative;
        max-width: 1440px;
        margin: auto;
    }

</style>
