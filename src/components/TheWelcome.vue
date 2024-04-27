<template>
  <div class="love">
    <div id="particles-js"></div>
    <h1 class="love-title text-gray-800">¡¡Feliz Aniversario❤️!!</h1>
    <p class="text-gray-600 text-3xl mt-2 px-10">
      Hace un mes en una noche, se dió pase a una relación muy hermosa que ya daba señales de lograrse desde un inicio.
      <br><br>
      Un 08 de febrero te conocí de la manera más hermosa e inexplicable, ambos con el mismo destino pero no imaginaríamos que nuestras vidas se unieran.
      Como si una fuerza nos juntara para conocernos.Sí fue Dios, a quién agradezco de haberme puesto en un vida.
      <br><br>
      Era el carnaval que nos unió y a pesar de estar poco tiempo contigo, me encantó tu forma de ser. Desde ese momento supe que eras una gran mujer, lo presentía en ese momento.
      <br><br>
      Poco a poco nos fuimos conociendo y en el proceso no me di por vencido, eras tú la mujer indicada. Quería que seas la persona a la que pueda compartir y expresar mis sentimientos.
      <br><br>
      El tiempo nos dió a conocer, que nuestras vidas mejoraban y que el amor estaba apunto de florecer.
      Hasta que llegó el momento donde empezaríamos a escribir una historia informal de dos personas enamoradas.
      <br><br>
      Es tan mágico pasar a tu lado, cada día aprendemos nuevas cosa, tenemos experiencias, nos reímos, nos ponemos románticos, nos cuidamos el uno del otro y mucho más.
      <br><br>
      Qué rápido ha pasado un mes, tiempo donde demostramos que estamos muy enamorados y somos felices a cada momento.
      <br><br>
      Hoy en nuestro día, sé lo importante que eres para mí. Eres el amor de mi vida, la persona con quién quiero compartir el tiempo, a la que quiero proteger y decirle que todo estará bien, la que veré triunfar (porque sé que serás una enfermera) y estaré presente para decirte "Felicidades mi amor, lo lograste".
      <br><br>
      Eres una gran mujer de gran corazón. Mi vida cambió para bien desde que te conocí, no sabes lo agradecido que estoy contigo.
      Tenemos mucho por lograr mi amor. Juntos de la mano, lograremos nuestros propósitos y ser felices en el futuro, en esa casita en la selva donde viviremos :D.
      <br><br>
      Gracias por haber confiado en mí y haberme entregado tu corazón. Te prometo que lo cuidaré muy bien, porque es un tesoro muy valioso para mí.
      <br><br>
      Estoy enamorado de ti, cada día pienso más en ti y me encantaa. Te haré la mujer más feliz del mundo porque mereces todo lo que una gran mujer debe tener. Y yo, como tu enamorado me encargaré de que sea así. Llegué a tu vida para quedarme y protegerte porque estoy orgulloso de que seas mi enamorada.
      <br><br>
      <b>Feliz primer mes, amor mío!! Con mucho gusto puedo decirte que...</b>
      <br><br>
    </p>
    <h1 class="love-title text-red-800">TE AMOOOOO❤️!!!</h1>
    <div class="flex justify-center w-100 mb-2">
      <img width="250" class="text-center" src="../assets/images/juntos.jpg" alt="">
    </div>
  </div>
</template>
<script setup>
// import particle from "../utils/particles.json";
const particle = {
  particles: {
    number: { value: 12, density: { enable: true, value_area: 500 } },
    color: { value: "#fff" },
    shape: {
      type: "image",
      stroke: { width: 0, color: "#000000" },
      polygon: { nb_sides: 5 },
      image: {
        src:
          "https://www.clipartmax.com/png/full/10-108819_preview-minus-dibujos-de-globos-en-forma-de-corazon.png",
        width: 125,
        height: 250,
      }
    },
    // opacity: {
    //   value: 0.5,
    //   random: true,
    //   anim: { enable: false, speed: 1, opacity_min: 0.1, sync: false }
    // },
    // size: {
    //   value: 40,
    //   // random: true,
    //   anim: { enable: false, speed: 30, size_min: 0.1, sync: false }
    // },
    // line_linked: {
    //   enable: false,
    //   distance: 500,
    //   color: "#ffffff",
    //   opacity: 0.4,
    //   width: 2
    // },
    // move: {
    //   enable: true,
    //   speed: 1,
    //   direction: "bottom",
    //   random: false,
    //   straight: false,
    //   out_mode: "out",
    //   bounce: false,
    //   attract: { enable: false, rotateX: 600, rotateY: 1200 }
    // }
  },
  // interactivity: {
  //   detect_on: "canvas",
  //   events: {
  //     onhover: { enable: true, mode: "bubble" },
  //     onclick: { enable: true, mode: "repulse" },
  //     resize: true
  //   },
  //   modes: {
  //     grab: { distance: 400, line_linked: { opacity: 0.5 } },
  //     bubble: { distance: 400, size: 10, duration: 0.3, opacity: 1, speed: 3 },
  //     repulse: { distance: 200, duration: 0.4 },
  //     push: { particles_nb: 4 },
  //     remove: { particles_nb: 2 }
  //   }
  // },
  // retina_detect: true
};
console.log("particle", particle);
const loadParticles = async () => {
  const head = document.getElementsByTagName("head")[0];
  const cssId = "particle";
  if (!document.getElementById(cssId)) {
    const link = document.createElement("script");
    link.id = cssId;
    link.type = "text/javascript";
    link.src = "https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js";
    head.appendChild(link);
    setTimeout(() => {
      window.particlesJS("particles-js", particle);
    }, 500);
  }
};
loadParticles();
</script>
