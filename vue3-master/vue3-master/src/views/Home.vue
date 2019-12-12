<template>
  <div class="row">
    <div class="col-8">

      <InstagramCard :key="a" :info="a" v-for="a in trazi"/>

    </div>
    <div class="col-4">
      Kao neki sidebar
    </div>
  </div>
</template>

<script>
import InstagramCard from '@/components/InstagramCard.vue'
import store from '@/store.js'
export default {
   data() {
 return {
 cards: [
 { id:'bice bolje',title: 'jedan', time: 'an hour ago', url: 'https://picsum.photos/id/1012/400/400' },  
 { id:'drugi puta',title: 'dva', time: '2 days ago', url: 'https://picsum.photos/id/1011/400/400' }, 
  { id:'nismo se snasli',title: 'tri', time: '3 days ago', url: "https://picsum.photos/id/1013/400/400" }, 
 ]
 }
 },
 computed:{
   trazi(){
   return this.cards.filter(nesto=>nesto.title.includes(store.searchTerm)||nesto.id.includes(store.searchTerm))
   }
 },
  name: 'home',
  components: {
    InstagramCard
  }
}
</script>

<style lang="scss">

.card-body {
  padding: 0px;
}

</style>