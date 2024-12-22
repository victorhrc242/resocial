
<template>
  <div>
    <Baner/>
    <h1>Noticias</h1>
    <Cards1/>
    <h1>Reviews TV</h1>
    <Noticias/>
    <h1>Review wiki</h1>
    <ReviewWiq/>
    <h1>ANÁLISES</h1>
    <Analises/>
    <Rodape/>
  </div> 
</template>
<script>
import Baner from '@/components/Baner.vue';
import Cards1 from '@/components/Cards1.vue';
import Noticias from'@/components/Noticias.vue';
import ReviewWiq from '@/components/ReviewWiq.vue';
import Analises from'@/components/Analises.vue';
import Rodape from '@/components/Rodape.vue';
export default {
  components: {
    Baner,
    Cards1,
    Noticias,
    ReviewWiq,
    Analises,
    Rodape,
  },
};
</script>
