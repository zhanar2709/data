<template>
  <div id="app">
    <div class="nav">
      <div class="logo">
        <img src="./assets/logo.png" height="40" width="40" alt="">
      </div>
      <div class="navigators">
        
            
          <a href="#">ЗЕМЛЯ</a>
          <a href="#">ТЕХНОЛОГИИ</a>
          <a href="#">КОСМОС</a>
          <a href="#">ФИЗИКА</a>
          <a href="#">ХИМИЯ</a>
          <a href="#">СПОРТ</a>
          
            
          <input placeholder="Что вы ищете?" class="www" type="text">
          <i class="material-icons">search</i>
          <i class="material-icons" style="font-size:30px;color:red ">add_alert</i>
          
          <span class="glyphicon glyphicon-search"></span>
        
      </div>
    </div>



    <section class="head">

    <div class="hea">
      
    <div class="headContent">
      <h6>TOP STORIES</h6>
      <h2>Мировые океаны
прогреваются на 13%
быстрее, чем раньше</h2>
      <a href="#">Читать дальше</a>
    </div>

    <div class="headCont">
      <div><p>01</p><p>Эта краска для волос меняет цвет в зависимости от температуры вокруг вас</p></div>
     
      <div><p>02</p><p>Это видео показывает одну из самых опасных угроз, стоящих перед человечеством</p></div>
      <div><p>03</p><p>Астрономы выпустили 3D-карту пыли Млечного Пути</p></div>
     
      

    </div>
      </div>
    </section>

    <section class="trend">

      <div class="trendContent">
        

        <p class="trendHeader">в тренде</p>

        <div class="news">
          <div class="newsContent">
            <img src="./assets/a.png" alt="">
            <p class="categ blue">ТЕХНОЛОГИИ</p>
            <p>Простой трюк, чтобы лучше всего выглядеть на селфи</p>
          </div>

          <div class="newsContent">
            <img src="./assets/b.png" alt="">
            <p class="categ green">ЗЕМЛЯ</p>
            <p>Взгляд астронавта на недавнее вулканическое извержение вулкана Этны</p>
          </div>


          <div class="newsContent">
            <img src="./assets/c.png" alt="">
            <p class="categ sky">ФИЗИКА</p>
            <p>Подземный инструмент будет измерять, сколько земли перетаскивает пространство</p>
          </div>

          <div class="newsContent">
            <img src="./assets/d.png" alt="">
            <p class="categ purple">ХИМИЯ</p>
            <p>Формы первой жизни могут не нуждаться в фосфате</p>
          </div>
          
        </div>
        
      </div>



      



    </section>

    <section class="paper">
      <p class="trendHeader">ПОСЛЕДНИЕ СТАТЬИ</p>

      <div class="newses" v-for="item in news">
        
        <div class="prod">
          <div class="img">
            <img :src="item.img" width="100%" alt="">
            
          </div>
          <div class="iii">
            <p class="categ purple">{{ item.category }}</p>
            <h3>{{item.title.substring(0,45)}}...</h3>
            <p>{{ item.text.substring(0,115) }}...</p>
            <hr id="asd">
            <div class="prodFooter">
              <p class="date">{{item.date}}</p>
              <img src="./assets/positive.png" height="32" width="32" alt="">
            </div>

          </div>

          

          
        </div>

        







      </div>

    </section>



  </div>
</template>

<script>
import axios from 'axios';
  import Vue from 'vue'
import newss from './news.json'
export default {
  name: 'app',
  data () {
    return {
      news: newss,
      ggg: '',


    }
  },
  methods:{
    asd(){
      let nnn = []
    for (var i = 0; i < this.news.length; i++) {
      nnn.push(this.news[i].text);
    }
    
    
    let sss =  axios.post('https://apiv2.indico.io/sentiment/batch',JSON.stringify({
    'api_key': "e20d0cddbd069f4e16d8ee6204b80851",
    'data': nnn
      })).then(res=>{return res.data}) 
          .catch(function (error) {
            console.log(error);
          });




    console.log(sss);

  
    }
  },
  created(){

    console.log(this.asd());

    

  }
  
};
</script>

<style>
#app{
  position: relative;
}

.nav{
  padding:  15px;
position: absolute;
  width: 100%;
  display: flex;
  justify-content: space-between;
}
.logo{
  border: 2px solid black;
  border-radius: 5px;

  background-color: gray;
  opacity: 0.2;
}

.navigators a{
  margin-right: 10px;
  text-decoration: none;
  color: black;
  
}

.navigators img {
  width: 40px;
}

.www{
  background: transparent;
            border-top: transparent;
            border-left: transparent;
            border-right: transparent;
            border-bottom: 1px solid;
            font-weight: 200;
            color: black;
            padding-left: 0;
}

.head{
  width: 100%;
  height: 100vh;
  background-image: url('assets/bg.png');
  position: 50% 50%;
  background-size: cover;
  display: flex;
  
}

.hea{
  align-self: flex-end;
  margin: 0 7%
}

.headContent{
  width: 40%;
  padding-bottom: 8%;
}



.headContent h2{
  font-weight: bold;
  color: white;
  font-family: 'Open Sans', sans-serif;
  font-size: 3em;
}
.headContent a, .headContent h6{
  color: white;
  

}

.headCont{
  display: flex;
  color: white;
}

.headCont div{
  padding: 15px;
}

.trend{
  
  width: 100%;
  height: 55vh;
  background-color: #e8e8e8;
}
.trendContent{
  padding: 0 8%;
}

.trendHeader{
  padding-top: 40px;
}

.news{
  display: flex;
  justify-content: space-around;
  margin:0;
  padding: 0;
}
.newsContent{
  width:  250px;
  

  font-family: 'Ubuntu Condensed', sans-serif;
  

}
.newsContent img{
  width: 100%;
  height: 160px;
  border-radius: 4px;
}

.newsContent p{
  margin: 0;
  padding: 0;
}

.categ{

}

.blue{
  color: blue;
}

.green{
  color: green;
}

.sky{
  color: #33c9dc;
}

.purple{
  color: purple;
}

.paper{
  margin: 0 20%;
}

.newses{
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.img{
  width: 800px  ;
}

.img img{
  width: 100%;
  height: 100%;
  object-fit: cover;

}

.prod{
  display: flex;
  box-shadow:0px 1px 10px 1px grey; 
  width: 100%;
  height: auto;
  margin: 30px 0;
}

.iii{
  padding: 40px;
}

.prodFooter{
  display: flex;
  justify-content: space-between;
}

.prodFooter img{
  background-color: red;
}

.ggg{
  width: 200px;
  

}
</style>
