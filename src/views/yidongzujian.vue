<template>
  <div class="divdiv" v-if="showContent">
    <h3 class="title">移动++++++++++++++组件++++</h3>
    <nav class="navigation">
      <router-link to="/geleizujian" class="nav-link">跳转到各类组件</router-link>
    </nav>
   
    <hr>
    <VantDizhi></VantDizhi>
    <Danmu></Danmu>
  </div>
</template>

<script>
import VantDizhi from '../newnewcomponents/vantdizhi.vue';
import Danmu from '../newnewcomponents/danmu.vue';
export default {
  name: 'geleizujian',
  components: {
    VantDizhi,
    Danmu
  },
  data() {
    return {
      showContent: false,
    }
  },
  mounted() {
    setTimeout(() => {
      this.showContent = true;
    }, 0);
  }
}
</script>

<style scoped>
.divdiv {
  position: relative;
  z-index: 10;
}

.title {
  color: red;
  margin-bottom: 20px;
}

.navigation {
  margin: 20px 0;
  z-index: 11;
}
</style>
