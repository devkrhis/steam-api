<template>
  <div id="app">
    <div class="generalBox">
      <h1> Olá Seja bem vindo ao Mundo do CHUCK NORRIS!</h1>
      <div class="img-chucknorris">
        <a  href="https://api.chucknorris.io/"> <img src="./imgs/chuck-norris.png" alt="Imagem do Chuck Norris"> </a>
      </div>
      <div class="jokeBox">
        <p> {{ this.dateArray.data.created_at }} </p>
        <span> <b>Joke:</b> {{ this.dateArray.data.value }} </span>
        <p> <a href=https://www.linkedin.com/in/krhistopher-kauling-novak-b4364712a> Clique para ser redirecionado </a></p>
      </div>
      <button class="button-56" type="button" onclick="history.go(0)"> Update Joke </button>
    </div>
  </div>
</template>


<script>

import events from './services/events';

export default {
  
  data(){
    return {
      dateArray: []
    }

  },


  mounted(){
    events.list().then(resposta => {
      console.log('resposta', resposta)
      this.dateArray = resposta
      console.log(this.dateArray.data.created_at, 'this.dateArray')

    })
  }

}
</script>

<style scoped>

.generalBox {
  display: flex;
  flex-direction: column;
  text-align: center;
  border: 3px solid grey;
  border-radius: 5%;
  margin-top: 50px;
  margin-bottom: 50px;
  margin-left: 400px;
  margin-right: 400px;
}

.img-chucknorris{
  display: flex;
  justify-content: center;
}

.img-chucknorris img{
  width: 150px;
}

.jokeBox{
  text-align: center;
}

button {
  display: flex;
  text-align: center;
  justify-content: center;
  width: 50%;
  margin-left: 25%;
  margin-bottom: 10px;
}
/* CSS */
.button-56 {
  align-items: center;
  background-color: #fee6e3;
  border: 2px solid #111;
  border-radius: 8px;
  box-sizing: border-box;
  color: #111;
  cursor: pointer;
  display: flex;
  font-family: Inter,sans-serif;
  font-size: 16px;
  height: 48px;
  justify-content: center;
  line-height: 24px;
  max-width: 100%;
  padding: 0 25px;
  position: relative;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-56:after {
  background-color: #111;
  border-radius: 8px;
  content: "";
  display: block;
  height: 48px;
  left: 0;
  width: 100%;
  position: absolute;
  top: -2px;
  transform: translate(8px, 8px);
  transition: transform .2s ease-out;
  z-index: -1;
}

.button-56:hover:after {
  transform: translate(0, 0);
}

.button-56:active {
  background-color: #ffdeda;
  outline: 0;
}

.button-56:hover {
  outline: 0;
}

@media (min-width: 768px) {
  .button-56 {
    padding: 0 40px;
  }
}

</style>
