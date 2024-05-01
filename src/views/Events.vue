<template>
  <div class="carta mt-20">
    <div
      class="container-letter"
      @click="open"
    >
      <div class="cover"></div>
      <span class="heart">♥</span>
      <p
        class="paper text-center"
        id="mainMessage"
      >
        <span><b>FELIZ DÍA DEL TRABAJADOR, MI AMOR</b></span>
        <br />
        Por todo lo que hiciste y haces para salir adelante, por todo lo que aún sin experiencia le dices "sin miedo al
        éxito" y lo intentas hasta que te salga. Por tu perseverancia y constancia para hacer cosas sin pedir nada a
        cambio, por las acciones que realizas nacidas de ti. Por tu fortaleza en situcianos difíciles para poder
        levantarte. Por tu entrega y lucha por nuestro amor. Por todo eso y mucho más. Feliz día del trabajador! 💪
        <br />
        <span class="text-red-600"><b>TE AMO MUCHO</b></span>
        <br />
        <span
          class="float-end"
          @click="close"
          ><b>Atte: Tu jefe</b></span
        >
      </p>
      <div class="letter"></div>
    </div>
    <div class="options">
      <!-- <button
        id="open"
        @click="open"
      >
        Abrir
      </button> -->
      <!-- <button
        id="close"
        @click="close"
      >
        Cerrar
      </button> -->
    </div>
  </div>
</template>
<script>
const btnOpenElement = document.querySelector("#open");
const btnCloseElement = document.querySelector("#close");
export default {
  data() {
    return {};
  },
  mounted() {
    setTimeout(() => {
      this.open();
    }, 2000);
  },
  methods: {
    open() {
      //   btnOpenElement.disabled = true;
      //   btnCloseElement.disabled = false;
      const coverElement = document.querySelector(".cover");
      coverElement.classList.add("open-cover");

      setTimeout(() => {
        //
        coverElement.style.zIndex = -1;

        const paperElement = document.querySelector(".paper");
        paperElement.classList.remove("close-paper");
        paperElement.classList.add("open-paper");

        // animacion del corazón
        const heartElement = document.querySelector(".heart");
        heartElement.style.display = "block";
      }, 500);
    },
    close() {
      //   btnOpenElement.disabled = false;
      //   btnCloseElement.disabled = true;

      const coverElement = document.querySelector(".cover");
      const paperElement = document.querySelector(".paper");
      paperElement.classList.remove("open-paper");
      paperElement.classList.add("close-paper");

      setTimeout(() => {
        coverElement.style.zIndex = 0;
        coverElement.classList.remove("open-cover");

        // animacion del corazón
        const heartElement = document.querySelector(".heart");
        heartElement.style.display = "none";
      }, 500);
    },
  },
};
</script>
<style>
/* reset css */

* {
  min-width: 0;
  font: inherit;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100dvh;
}

h1,
h2,
h3 {
  text-wrap: balance;
}

p {
  text-wrap: pretty;
}

body {
  background: url("https://img.freepik.com/foto-gratis/vista-superior-composicion-escritorio-elegante_23-2148975800.jpg?size=626&ext=jpg&ga=GA1.1.672697106.1714262400&semt=ais");
}

.carta {
  display: flex;
  flex-direction: column;

  gap: 3rem;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container-letter {
  position: relative;
}

.cover {
  position: absolute;
  border-left: 200px solid transparent;
  border-right: 200px solid transparent;
  border-top: 180px solid #fe3334;
  border-bottom: 100px solid transparent;

  /*  */
  transition: transform 0.75s;
  transform-origin: top;
}

.paper {
  position: absolute;
  padding: 1rem;
  font-size: 0.9em;
  line-height: 1.5rem;
  right: 5px;
  /*  */
  z-index: -1;
  /* background: white; */
  /* background-size: auto; */
  background: #ffffff;
  width: 390px;
  height: 290px;
  transition: all 0.75s;
}

.letter {
  border-left: 200px solid #ff989e;
  border-right: 200px solid #ff989e;
  border-top: 150px solid transparent;
  border-bottom: 130px solid #ff858a;
}

.options {
  display: flex;
  gap: 5rem;

  & button {
    color: #ff3234;
    font-weight: 600;
    border-radius: 3px;
    background: #fad7df;
    padding: 0.5rem 1rem;
    border: 1px solid #fe3334;
    cursor: pointer;
  }

  & button:hover {
    background: #ff989e;
    color: white;
  }
}

.open-cover {
  transform: rotatex(180deg);
}

.open-paper {
  animation: openPaper 2s forwards;
}

@keyframes openPaper {
  0% {
    top: 0;
  }
  50% {
    top: -300px;
  }
  100% {
    top: -100px;
    z-index: 2;
  }
}

.close-paper {
  animation: closePaper 0.5s forwards;
}

@keyframes closePaper {
  0% {
    top: -180px;
  }
  100% {
    top: 0;
  }
}

.heart {
  display: none;
  position: absolute;
  top: 25%;
  left: 46.5%;
  margin: auto;
  font-size: 3rem;

  color: #fe3334;

  animation: crecer 2s forwards;
}

@keyframes crecer {
  0% {
    scale: 1;
    opacity: 1;
  }
  100% {
    scale: 3;
    opacity: 0;
  }
}
</style>
