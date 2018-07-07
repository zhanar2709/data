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
        <a href="#">РАЗВИТИЕ</a>
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
          <div class="qwe"><p>01</p><p>Эта краска для волос меняет цвет в зависимости от температуры вокруг вас</p></div>

          <div class="qwe"><p>02</p><p>Это видео показывает одну из самых опасных угроз, стоящих перед человечеством</p></div>
          <div><p>03</p><p>Астрономы выпустили 3D-карту пыли Млечного Пути</p></div>



        </div>
      </div>
    </section>

    <section class="trend">

      <div class="trendContent">


        <p>в тренде</p>

        <div class="news">

        </div>

      </div>







    </section>



  </div>
</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
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





  .qwe {
    border-right: 1px solid white;
  }




  .head{
    width: 100%;
    height: 100vh;
    background-image: url('assets/bg.png');
    position: 50%;
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
    font-family: 'Rubik Mono One', sans-serif;

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
    height: 45vh;
    background-color: #e8e8e8;
  }
  .trendContent{
    padding: 0 8%;
  }

  .news{
    padding-top: 40px;
  }
</style>
