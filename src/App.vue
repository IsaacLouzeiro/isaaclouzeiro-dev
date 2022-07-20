<template>
    <div>
        <nav>
            
        </nav>
        
        <router-view/>
    </div>
</template>

<style lang="scss">
    // standard
    
    @import url('https://fonts.googleapis.com/css2?family=Ubuntu:ital,wght@0,300;0,500;0,700;1,300;1,400;1,500;1,700&display=swap'); // mbuntu font
    @import '@/assets/colors/colors.scss'; // colors

    .gradient { background-image: linear-gradient(to bottom right, $color-d-2, $color-l-2) } // main gradient

    a { &:hover { text-decoration: none; opacity: .7 } }; // link hover
    ul { list-style-type: none; } // list without style type

    * { // space and font
        margin: 0;
        padding: 0;
        font-family: 'Ubuntu', 'Trebuchet MS', sans-serif;
    }

    html, body { width: 100%; height: 100%; }

</style>
