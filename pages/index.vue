<template>
  <div class="main">
    <NavbarTemplate />
    <main>
      <a v-for="(d,i) in data" :key="i" class="card flex-row rounded mb-3 " :href="'/read/'+d.title">
        <img :src="d.img" alt="image" class="rounded">
        <div class="wraper">
          <h3>{{ d.title }}</h3>
          <p>{{ d.content }}</p>
        </div>
      </a>
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
      }
    }
  }
</script>

<style>
  body{
    background-color: gainsboro;
  }

  div.main{
    padding: 3%;
    display: flex;
    flex-direction: column;
    height: 100vh;
    width: 100vw;
  }

  main{
    height: 100vh;
    width: 100%;
    overflow-y: auto;
  }

  .card{
    width: 100%;
    height: auto;
    text-decoration: none;
  }

  .wraper{
    width: 100%;
    height: auto;
    margin-left: 1%;
  }

  .wraper p, .wraper h3{
    width: 100%;
  }
  .wraper p{
    height: 6vh;
    overflow: hidden;
  }

  .card img{
    min-width: 123px;
    width: 12vw;
  }

</style>