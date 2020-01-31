<template>
  <div id="app">
    <img class="logo" alt="Vue logo" src="./assets/logo.png">

    <div class="container">
      <button v-on:click="priceSort" class="btn btn-danger">가격정렬</button>
      <button class="btn btn-danger">이름순정렬</button>
      <button class="btn btn-danger">원래대로</button>
    </div>

    <!-- 1주차 배운내용 -->
    <!-- 프로젝트생성법 vue create 프로젝트명
    {{}}
    v-bind : 
    Component만드는 법 (쩜vue파일 만든 후 3 스텝) 
    props (3 스텝)
    v-on:click=""
     -->



    <div class="container">
      <div class="row">
        <Card v-for="(자료,i) in 원룸들" v-bind:원룸들="자료" :key="i"></Card>
        <!-- <Card v-bind:원룸들="원룸들[1]"></Card>
        <Card v-bind:원룸들="원룸들[2]"></Card>
        <Card v-bind:원룸들="원룸들[3]"></Card>
        <Card></Card>
        <Card></Card> -->
      </div>
    </div>

    <!-- <p v-bind:style="빨간색">{{ 인삿말 }}</p> -->

    <!-- 반복문이랑 데이터바인딩 연습 -->
    <!-- <h4 v-for="자료 in [1,2,3]" :key="자료">{{자료}}</h4>

    <div v-for="자료 in posts" :key="자료">
      <h4>{{ 자료.title }}</h4>
      <p>{{ posts[0].date }}</p>
    </div>

    <h4>{{ posts[1].title }}</h4>
    <p>{{ posts[1].date }}</p>

    <h4>제목</h4>
    <p>날짜</p> -->

  </div>
</template>

<script>
//document.getElementById().innerHTML = ??;
// import HelloWorld from './components/HelloWorld.vue'

import Card from './components/Card.vue'
import data from './assets/data.js'

export default {
  name: 'app',
  data(){
    return {
      원룸들 : data,
      인삿말 : '안녕하세요',
      인삿말2 : '하이',
      빨간색 : 'color : blue;',
      posts : [
        {
          title : '오늘의 일기',
          date : '4월 20일'
        },
        {
          title : '수분크림 추천',
          date : '3월 4일'
        },
        {
          title : '강남 맛집 후기',
          date : '2월 22일'
        }
      ],

    }
  },
  components: {
    Card,
    //HelloWorld
  },
  computed : {
    
  },
  watch : {

  },
  methods: {
    priceSort(){
      // var 어레이 = [5,3,4,1,2];
      // 어레이.sort(function(a,b){
      //   return a - b
      // });
      //원룸들 = [{},{},{},{}]
      this.원룸들.sort(function(a,b){
        return a.price - b.price
      });
      //원룸들이라는 데이터를 정렬 해주셈 ~
    },
    sortBack(){

    },
  }
}
</script>

<style>
/* @import './' */

.logo {
  width: 100px;
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
