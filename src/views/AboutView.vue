<template>
  <div class="about flex justify-center items-center">
    <div class="px-5 text-center">
      <div class="text-3xl font-bold text-gray-800">
        Solo puede desbloquearlo con la fecha de nacimiento de su novio...
      </div>
      <br />
      <div class="">
        <VueDatePicker
          v-model="date"
          auto-apply
          partial-flow
          :flow="['calendar']"
          :enable-time-picker="false"
        ></VueDatePicker>
      </div>
      <div
        class="mt-3"
        v-if="date"
      >
        <button
          @click="validate"
          class="bg-red-500 hover:bg-white hover:text-red-300 text-white font-bold py-2 px-4 rounded"
        >
          VALIDACIÓN DE AMOR
        </button>
      </div>
      <div class="text-center flex justify-center mt-3">
        <img
          v-if="status === 1"
          width="150"
          src="../assets/images/enojada.webp"
          alt=""
        />
      </div>
      <div
        v-if="status === 2"
        class="flex justify-between w-100 relative"
      >
        <img
          id="image1"
          src="../assets/images/mickey2.png"
          class="img-fluid"
          alt=""
        />
        <img
          id="image2"
          src="../assets/images/minie2.png"
          class="img-fluid"
          alt=""
        />
      </div>
      <div class="text-2xl font-bold mt-2 text-gray-800">
        {{ msge }}
      </div>
    </div>
  </div>
</template>
<script>
import VueDatePicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";
export default {
  components: { VueDatePicker },
  data() {
    return {
      date: null,
      msge: "",
      status: 0,
    };
  },
  methods: {
    validate() {
      console.log("this.date", this.date);
      const dateFormat = new Date(this.date);
      const dateActual = dateFormat.toISOString();
      const date = dateActual.slice(0, 10);
      console.log("dateFormat", date);
      if (date === "1997-09-15") {
        this.status = 2;
        setTimeout(() => {
          this.msge = "MUY BIEN HECHO AMOR!!";
          const image1 = document.getElementById("image1");
          const image2 = document.getElementById("image2");

          // Mover las imágenes gradualmente hacia el centro
          let currentPosition1 = 0;
          let currentPosition2 = 0;

          const moveImages = setInterval(function () {
            currentPosition1 += 1;
            currentPosition2 -= 1;

            image1.style.left = currentPosition1 + "px";
            image2.style.left = currentPosition2 + "px";

            if (currentPosition1 >= 30 && currentPosition2 <= 30) {
              clearInterval(moveImages); // Detener la animación al juntarse las imágenes
              console.log("Imágenes juntas en el centro");
            }
          }, 10);
        }, 500);
        setTimeout(() => {
          this.msge = "ESTÁS A NADA DE VER LO QUE DICE MI CORAZÓN";
          this.msge = "POR LO QUE HOY SIGNIFICA PARA NOSOTROS";
        }, 2500);
        setTimeout(() => {
          this.msge = "POR TU MES TAN ESPECIAL";
        }, 4500);
        setTimeout(() => {
          this.msge = "POR QUE SIEMPRE FUISTE LEAL DESDE EL INICIO";
        }, 6500);
        setTimeout(() => {
          this.msge = "MI SECRETARIA SE MERECE ESTO...";
          this.$router.push({ name: "events" });
          this.date = null;
        }, 8500);
      } else {
        this.status = 1;
        this.msge = "PI PI PI PI";
        setTimeout(() => {
          this.msge = "";
          this.status = 0;
        }, 2000);
      }
    },
  },
};
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
