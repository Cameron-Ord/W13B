<template>
  <div>
    <header class="Page_Header"><page-header></page-header></header>
    <main class="Page_Main"><display-posts></display-posts></main>
    <footer class="Page_Footer"><page-footer></page-footer></footer>
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue';
import DisplayPosts from './components/DisplayPosts.vue';
import PageFooter from './components/PageFooter.vue';
export default {
  name: 'page_comps',
  components: {
 
    PageHeader,
    DisplayPosts,
    PageFooter

  }
}
</script>

<style>

*{

  padding: 0px;
  margin: 0px;
}


.Page_Header{

display:grid;

grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

justify-items: center;

align-items: center;

min-height: 10vh;
}


.Page_Main{

display: grid;

grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

min-height: 80vh;

justify-items: center;

align-items: center;


}


.Page_Footer{

display: grid;

grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

justify-items: center;

align-items: center;

min-height: 10vh;
}
</style>
