<template>
    <div>
        <!-- open navbar button -->
        <button class="btn bar" type="button" data-bs-toggle="offcanvas" data-bs-target="#menuMobile" aria-controls="menuMobile" ><font-awesome-icon icon="fa-solid fa-bars" /></button>

        <div class="offcanvas offcanvas-start text-bg-dark" data-bs-scroll="true" tabindex="-1" id="menuMobile" aria-labelledby="menuMobileLabel">
            <div class="offcanvas-header">
                <!-- language -->
                <div class="btn-group dropend">
                    <button type="button" class="btn lang" data-bs-toggle="dropdown" aria-expanded="false">
                        <font-awesome-icon icon="fa-solid fa-language" />
                    </button>
                    <ul class="dropdown-menu">
                        <!-- Dropdown menu links -->
                        <li 
                            class="dropdown-item" 
                            v-for="(lang, index) in language" 
                            :key="index" 
                            :class="{ disabled: lang.isCheck }"

                            @click="changeTo(index)"
                        >
                            <button type="button">{{ lang.name }}</button>
                        </li>
                    </ul>
                </div>

                <!-- close navbar button -->
                <button type="button" class="bar-close" data-bs-dismiss="offcanvas" aria-label="Close"><font-awesome-icon icon="fa-solid fa-bars" /></button>
            </div>
            <!-- navbar mobile content -->
            <div class="offcanvas-body">
                <!-- navbar mobile list -->
                <ul class="nav flex-column">
                    <li class="nav-item"><a href="#" class="nav-link"><font-awesome-icon icon="fa-solid fa-house-chimney" /> Home</a></li>
                    <li class="nav-item"><a href="#about" class="nav-link"><font-awesome-icon icon="fa-solid fa-book-open-reader" /> About</a></li>
                    <li class="nav-item"><a href="#work" class="nav-link"><font-awesome-icon icon="fa-solid fa-code" /> Work</a></li>
                    <li class="nav-item"><a href="#contact" class="nav-link"><font-awesome-icon icon="fa-solid fa-envelope" /> Contact</a></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavbarContent',
    data() {
        return {

        }
    },
    props: {
        language: Array
    },
    methods: {
        changeTo(i) {
            if(i == 0) this.$emit('changeTo', 'English')
            else if(i == 1) this.$emit('changeTo', 'Portuguese')
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '@/assets/colors/colors.scss'; // colors

    // all buttons
    button {
        padding: 0;
        margin: 0;
        background-color: rgba(0,0,0,0);
        border: none;
        font-size: 1.9em;
        color: $color-l-1;

        // bar button
        &.bar {
            color: $color-l-1;
        }
        // lang button
        &.lang {
            color: $color-l-3;
        }
    }

    // change language button
    .dropdown-menu {
        background-color: rgba($color-l-3, 1);
        .dropdown-item {
            padding: 0;
            button {
                font-size: 1em;
                color: $color-l-1;
                width: 100%;
                padding: 3px 0 3px 10px;
                text-align: start;

                &:hover, &:active {
                    background-color: $color-l-1;
                    color: $color-d-1;
                }
            }

            &.disabled {
                background-color: rgba($color-l-1, .3);
            }
        }
    }

    // navbar mobile width content
    .offcanvas {
        width: 20rem;
    }
    
    @media only screen and (max-width: 576px) {
        .offcanvas {
            width: 15rem;
        }
    }
    // navbar mobile list content
    .nav {
        .nav-item {
            .nav-link {
                padding: 5px 0;
                margin: 5px 0;
                color: $color-l-1;
                text-decoration: underline;
                text-decoration-color: $color-l-2;

                svg {
                    margin-right: 10px;
                }
            }
        }
    }
</style>