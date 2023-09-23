<template>
    <div class="wraper">
        <NavbarTemplate />
        <main class="rounded">
            <h1 class="mb-4"> {{ show.title }}</h1>
            <img :src="show.img" alt="" class="mb-4">
            <p>{{ show.content }}</p>
        </main>
        <FooterTemplate />
    </div>
</template>

<script>
    import NavbarTemplate from '~/components/NavbarTemplate.vue';
    import FooterTemplate from '~/components/FooterTemplate.vue';

    const data = [
        {
            title:"Judul Artikel 1",
            content :"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
            img: 'https://images.unsplash.com/photo-1649282806617-c51bb282899c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80'
        },
        {
            title:"Judul Artikel 2",
            content :"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
            img: 'https://images.unsplash.com/photo-1635732646038-0a1a2fe3f2d6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80'
        },
        {
            title:"Judul Artikel 3",
            content :"Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
            img: 'https://images.unsplash.com/photo-1640006807976-a6127e9d6fa0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1171&q=80'
        },
    ];

    export default {
        components:{
            FooterTemplate,
            NavbarTemplate,
        },
        data(){
            return{
                data,
                show:{},
            }
        },
        mounted(){
            this.show = this.sinkron;
        },
        computed:{
            sinkron(){
                return data.find(a => {
                    return a.title === this.$route.params.title;
                });
            }
        }
    }
</script>

<style>
    body{
        background-color: gainsboro;
    }
    main{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        background-color: whitesmoke;
        padding: 3%;
    }
    .wraper{
        width: 100vw;
        height: auto;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        padding: 3%;
    }
    main img{
        width: 30%;
    }
</style>