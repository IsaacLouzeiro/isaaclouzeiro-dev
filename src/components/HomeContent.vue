<template>
    <div id="home">
        <div class="homeTextButtons">
            <div class="digitacao">
                <h2 class="boxText"><span class="text">{{ homeText[0] }}</span></h2><span class="barra">|</span>
            </div>
            <p>{{ homeText[1] }}</p>
    
            <ul class="nav">
                <li class="nav-item" v-for="(btn, index) in homeButtons" :key="index"><a :href="btn.link" class="nav-link btn" target="_blank">{{ btn.name }}</a></li>
            </ul>
        </div>

        <div class="homeIsaac">
            <img src="@/assets/img/me.jpeg" alt="Isaac Louzeiro">
            <h3>{{ homeIsaac[0] }}</h3>
            <p>{{ homeIsaac[1] }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HomeContent',
    props: {
        // home content
        homeText: Array,
        homeButtons: Array,
        homeIsaac: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '@/assets/colors/colors.scss';

    @import '@/assets/writingAnimation.scss';

    #home {
        width: 100%;
        height: 100%;
        max-height: 700px;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;

        .homeTextButtons {
            h2 { color: $color-l-1; }
    
            p { color: $color-l-3; }
    
            ul {
                li {
                    a {
                        background-color: $color-d-2;
                        color: $color-l-1;
                        margin-right: .5em;
                    }
                }
            }
        }

        .homeIsaac {
            display: flex;
            flex-direction: column;
            align-items: center;

            img {
                width: 10em;
                height: 10em;
                border-radius: 5em;
                border: 5px solid $color-l-3;
            }

            h3, p { color: $color-l-1; }

            h3 { margin-top: .5em; }

            p { font-size: 1.1em; font-style: italic; }
        }
    }
</style>