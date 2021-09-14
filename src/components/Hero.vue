<template>
    <a class="hero" :style="return_background_img(img)"  href="/">
        <div class="label">
            <div class="content">
                <img :src="return_atb_src(type) || sem_atb" height="10px" alt="">
                <span>{{ name }}</span>
            </div>
        </div>
    </a>
</template>

<script>

const atributos_source = [
    "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png",
    "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_intelligence.png",
    "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_agility.png",
]

export default {
    name: 'Hero',
    props: [ 'name', 'img', 'type'],
    data: () => {
        return {
            sem_imagem: "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png",
            sem_atb: "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png",
        }
    },
    methods: {
        return_atb_src: function(atb){
            if( atb=="s" ) return atributos_source[0]
            if( atb=="i" ) return atributos_source[1]
            if( atb=="a" ) return atributos_source[2]
            return ''
        },
        return_background_img: function(img_background){
            return { 'background-image': `url( ${img_background} )`}
        }
    }
}
</script>

<style lang="scss" scoped>
.hero {
    position: relative;
    height: 127px;
    width: 225px;
    display: inline-block;
    transition: ease 0.3s;
    box-shadow: 1px 1px 4px #000;

    //Image
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    .hero-photo {
        position: absolute;
        width: 100%;
        height: 100%;
        left: 0;
        top:0;
    }
    .label {
        img {
            width: 35px;
            height: 35px;
        }
        position: absolute;
        width: 100%;
        z-index: 1;
        bottom: 0;
        transform: translateY(30px);
        padding: 5px;
        opacity: 0;
        transition: ease 0.2s;

        .content{
            font-size: 100%;
            display: flex;
            align-items: center;
            gap: 5px;
        }
    }

    &:hover {
        z-index: 5;
        transform: scale(1.25);

        box-shadow:inset 0px -20px 30px black;

        .label {
            transform: none; 
            bottom: 0;
            opacity: 1;
        }
    }
}
</style>
